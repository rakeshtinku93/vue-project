<script lang="ts" setup>
import { computed, defineProps, ref } from 'vue'

const showFullDescription = ref(false)

const toggleDescription = () => {
  showFullDescription.value = !showFullDescription.value
}

const props = defineProps({
  job: {
    type: Object,
    required: true,
  },
})

const description = computed(() => {
  if (showFullDescription.value) {
    return props.job.description
  } else {
    return props.job.description.length > 100
      ? props.job.description.slice(0, 100) + '...'
      : props.job.description
  }
})
</script>

<template>
  <div class="bg-white rounded-xl shadow-md relative">
    <div class="p-4">
      <div class="mb-6">
        <div class="text-gray-600 my-2">{{ job.type }}</div>
        <h3 class="text-xl font-bold">{{ job.title }}</h3>
      </div>

      <div class="mb-5">
        {{ description }}
        <button @click="toggleDescription" class="text-green-900 hover:text-grreen-600 mb-5">
          {{ showFullDescription ? 'Less' : 'More' }}
        </button>
      </div>

      <h3 class="text-green-900 mb-2">{{ job.salary }} / Year</h3>

      <div class="border border-gray-100 mb-5"></div>

      <div class="flex flex-col lg:flex-row justify-between mb-4">
        <div class="text-blue-900 mb-3">
          <i class="pi pi-map-marker text-blue-900"></i>
          {{ job.location }}
        </div>
        <RouterLink
          :to="'/job/' + `${job.id}`"
          class="h-[36px] bg-green-900 hover:bg-green-600 text-white px-4 py-2 rounded-lg text-center text-sm"
        >
          Read More
        </RouterLink>
      </div>
    </div>
  </div>
</template>
