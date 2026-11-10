<template>
  <div
    v-if="tags.length"
    class="flex flex-row flex-wrap items-center gap-1"
  >
    <VBadge
      v-for="tag in tags"
      :key="tag.id"
      color="yellow"
      size="sm"
      :title="tag.definition"
    >
      {{ tag.label }}
    </VBadge>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { makeAPIRequest } from '@/utils'

const props = defineProps({
  otuId: {
    type: [Number, String],
    default: null
  },

  keyword_id: {
    type: [Number, String],
    default: null
  }
})

const tags = ref([])

async function loadTags(otuId) {
  try {
    const { data } = await makeAPIRequest.get('/tags', {
      params: {
        tag_object_type: 'Otu',
        tag_object_id: otuId,
        keyword_id: props.keyword_id
      }
    })

    tags.value = data.map(makeTag)
  } catch {}
}

function makeTag(tag) {
  return {
    id: tag.id,
    label: tag.keyword?.name || tag.object_tag || '',
    definition: tag.keyword?.definition || null
  }
}

onMounted(() => loadTags(props.otuId))
</script>
