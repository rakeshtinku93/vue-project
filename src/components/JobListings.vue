<script lang="ts" setup>
import jobs from '@/jobs.json'
import JobListing from '@/components/JobListing.vue'
import { ref, defineProps } from 'vue'

defineProps({
  limit: Number,
  showViewMore: {
    type: Boolean,
    default: false,
  },
})

const jobLists = ref(jobs)
</script>

<template>
  <section class="bg-green-50 px-4 py-10">
    <div class="container-xl lg:container m-auto">
      <h2 class="text-3xl font-bold text-green-900 mb-6 text-center">Browse Jobs</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <JobListing
          v-for="job in jobLists.slice(0, limit || jobLists.length)"
          :key="job.id"
          :job="job"
        ></JobListing>
      </div>
    </div>
  </section>

  <section class="m-auto max-w-lg my-10 px-6">
    <RouterLink
      v-if="showViewMore"
      to="/jobs"
      class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700"
      >View All Jobs</RouterLink
    >
  </section>
</template>
