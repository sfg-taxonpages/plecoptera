<!--
  Animated project counters for the homepage, modeled on the Orthoptera
  Species File homepage. Usage in pages/home.md:

    <HomeCounters :taxon-name-id="998323" />

  taxon-name-id: root taxon name of the project (Plecoptera Burmeister, 1839),
  used to count fossil species for "Valid extant species".
  items: optional list of counters to show, in order (keys of COUNTERS below);
  all are shown by default.

  Icons are from @jlpereira/taxonpages-module-homepage (MIT).
-->
<template>
  <section
    ref="sectionRef"
    class="bg-base-foreground"
  >
    <div class="container mx-auto">
      <div
        class="grid grid-cols-2 sm:grid-cols-4 auto-cols-fr xl:grid-flow-col py-10 lg:py-16 gap-10"
      >
        <div
          v-for="item in visibleCounters"
          :key="item.key"
          class="flex flex-col items-center px-4"
        >
          <component
            :is="item.icon"
            class="h-14 w-14 text-primary-color dark:text-base-content"
          />
          <div class="leading-3 text-center mt-5">
            <span class="font-medium text-2xl block tabular-nums">
              {{ displayed[item.key]?.toLocaleString() ?? '–' }}
            </span>
            <span class="uppercase text-sm">{{ item.label }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed, onBeforeUnmount, onMounted, reactive, ref } from 'vue'
import { makeAPIRequest } from '@/utils'

import IconBug from './icons/IconBug.vue'
import IconCitation from './icons/IconCitation.vue'
import IconImage from './icons/IconImage.vue'
import IconMicroscope from './icons/IconMicroscope.vue'
import IconOk from './icons/IconOk.vue'
import IconReference from './icons/IconReference.vue'

const SPECIES_RANK = 'NomenclaturalRank::Iczn::SpeciesGroup::Species'

// stat: key in the /stats response; counters without one are computed below
const COUNTERS = {
  validSpecies: { label: 'Valid species', icon: IconOk },
  validExtantSpecies: { label: 'Valid extant species', icon: IconOk },
  taxonNames: { label: 'Scientific names', icon: IconMicroscope, stat: 'Taxon names' },
  projectSources: { label: 'References', icon: IconReference, stat: 'Project sources' },
  citations: { label: 'Citations', icon: IconCitation, stat: 'Citations' },
  collectionObjects: { label: 'Specimen records', icon: IconBug, stat: 'Collection objects' },
  images: { label: 'Images', icon: IconImage, stat: 'Images' }
}

const ANIMATION_MS = 1200

const props = defineProps({
  taxonNameId: {
    type: Number,
    default: undefined
  },

  items: {
    type: Array,
    default: undefined
  }
})

const sectionRef = ref(null)
const counts = reactive({})
const displayed = reactive({})
let observer = null
let isVisible = false

const visibleCounters = computed(() =>
  (props.items || Object.keys(COUNTERS))
    .filter((key) => COUNTERS[key])
    .filter((key) => key !== 'validExtantSpecies' || props.taxonNameId)
    .map((key) => ({ key, ...COUNTERS[key] }))
)

function countTaxonNames(params) {
  return makeAPIRequest
    .get('/taxon_names.json', {
      params: { page: 1, per: 1, validity: true, rank: [SPECIES_RANK], ...params }
    })
    .then(({ headers }) => Number(headers['pagination-total']))
}

async function loadCounts() {
  const keys = visibleCounters.value.map((item) => item.key)
  const requests = []

  if (keys.some((key) => COUNTERS[key].stat)) {
    requests.push(
      makeAPIRequest.get('/stats').then(({ data }) => {
        keys.forEach((key) => {
          const value = data.data[COUNTERS[key].stat]

          if (value !== undefined) counts[key] = value
        })
      })
    )
  }

  if (keys.includes('validSpecies') || keys.includes('validExtantSpecies')) {
    requests.push(
      (async () => {
        const total = await countTaxonNames()

        counts.validSpecies = total

        if (keys.includes('validExtantSpecies')) {
          const fossils = await countTaxonNames({
            taxon_name_id: [props.taxonNameId],
            descendants: true,
            taxon_name_classification: ['TaxonNameClassification::Iczn::Fossil']
          })

          counts.validExtantSpecies = total - fossils
        }
      })()
    )
  }

  await Promise.allSettled(requests)
  if (isVisible) animate()
}

// Count up from zero once the section is on screen and the numbers are in
function animate() {
  const targets = { ...counts }
  let start = null

  const step = (timestamp) => {
    start ??= timestamp
    const progress = Math.min((timestamp - start) / ANIMATION_MS, 1)
    const eased = 1 - (1 - progress) ** 3

    Object.entries(targets).forEach(([key, value]) => {
      displayed[key] = Math.round(value * eased)
    })

    if (progress < 1) window.requestAnimationFrame(step)
  }

  window.requestAnimationFrame(step)
}

onMounted(() => {
  observer = new IntersectionObserver(
    ([entry]) => {
      if (!entry.isIntersecting) return

      isVisible = true
      observer.disconnect()
      if (Object.keys(counts).length) animate()
    },
    { threshold: 0.3 }
  )

  observer.observe(sectionRef.value)
  loadCounts()
})

onBeforeUnmount(() => observer?.disconnect())
</script>
