<template>
  <div class="container mx-auto py-4 px-4 sm:px-0">
    <h1 class="text-4xl font-bold">Recent</h1>

    <div class="flex flex-col gap-4 mt-4">
      <VCard>
        <VCardContent>
          <VSpinner v-if="taxonNames.isLoading" />
          <VTable>
            <VTableHeader>
              <VTableHeaderRow>
                <VTableHeaderCell>Taxon name</VTableHeaderCell>
              </VTableHeaderRow>
            </VTableHeader>
            <VTableBody>
              <VTableBodyRow
                v-for="item in taxonNames.list"
                :key="item.id"
              >
                <VTableBodyCell>
                  <RouterLink
                    v-if="item.otu"
                    :to="{ name: 'otus-id', params: { id: item.otu.id } }"
                    v-html="nameLabel(item)"
                  />
                  <span
                    v-else
                    v-html="nameLabel(item)"
                  />
                </VTableBodyCell>
              </VTableBodyRow>
            </VTableBody>
          </VTable>
          <VPagination
            v-model="taxonNames.pagination.page"
            class="mt-4"
            :total="taxonNames.pagination.total"
            :per="taxonNames.pagination.per"
            @update:model-value="loadTaxonNames"
          />
        </VCardContent>
      </VCard>

      <VCard>
        <VCardContent>
          <VSpinner v-if="sources.isLoading" />
          <VTable>
            <VTableHeader>
              <VTableHeaderRow>
                <VTableHeaderCell>Source</VTableHeaderCell>
              </VTableHeaderRow>
            </VTableHeader>
            <VTableBody>
              <VTableBodyRow
                v-for="item in sources.list"
                :key="item.id"
              >
                <VTableBodyCell v-html="item.cached" />
              </VTableBodyRow>
            </VTableBody>
          </VTable>
          <VPagination
            v-model="sources.pagination.page"
            class="mt-4"
            :total="sources.pagination.total"
            :per="sources.pagination.per"
            @update:model-value="loadSources"
          />
        </VCardContent>
      </VCard>
    </div>
  </div>
</template>

<script setup>
// Newest taxon names and sources added to the TaxonWorks project, following the
// Orthoptera Species File "Recent" page.
import { reactive, onMounted } from 'vue'
import { makeAPIRequest } from '@/utils'

const PER = 10

const taxonNames = reactive(makeList())
const sources = reactive(makeList())

function makeList() {
  return { list: [], isLoading: false, pagination: { page: 1, per: PER, total: 0 } }
}

function getPagination(headers) {
  return {
    page: Number(headers['pagination-page']),
    per: Number(headers['pagination-per-page']),
    total: Number(headers['pagination-total'])
  }
}

function nameLabel(item) {
  return [item.cached_html, item.cached_author_year].filter(Boolean).join(' ')
}

async function loadTaxonNames(page = 1) {
  taxonNames.isLoading = true

  try {
    const { data, headers } = await makeAPIRequest.get('/taxon_names', {
      params: {
        validity: true,
        recent: true,
        recent_target: 'created_at',
        taxon_name_type: 'Protonym',
        per: PER,
        page
      }
    })
    const { data: otus } = data.length
      ? await makeAPIRequest.get('/otus', { params: { taxon_name_id: data.map((item) => item.id) } })
      : { data: [] }

    taxonNames.pagination = getPagination(headers)
    taxonNames.list = data.map((item) => ({
      ...item,
      otu: otus.find((otu) => otu.taxon_name_id === item.id)
    }))
  } finally {
    taxonNames.isLoading = false
  }
}

async function loadSources(page = 1) {
  sources.isLoading = true

  try {
    const { data, headers } = await makeAPIRequest.get('/sources', {
      params: {
        in_project: true,
        recent: true,
        recent_target: 'created_at',
        per: PER,
        page
      }
    })

    sources.pagination = getPagination(headers)
    sources.list = data
  } finally {
    sources.isLoading = false
  }
}

onMounted(() => {
  loadTaxonNames()
  loadSources()
})
</script>
