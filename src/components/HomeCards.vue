<script lang="ts" setup>
import JobCard from '@/components/JobCard.vue'
import { RouterLink } from 'vue-router'

// export default {
//   components: {
//     JobCard,
//   },
// }
</script>

<template>
  <section class="py-4">
    <div class="container-xl lg:container m-auto">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
        <JobCard background="bg-gray-100">
          <h2 class="text-2xl font-bold">For Developers</h2>
          <p class="mt-2 mb-4">Browse our Vue jobs and start your career today</p>
          <RouterLink
            to="/jobs"
            class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700"
          >
            Browse Jobs
          </RouterLink>
        </JobCard>
        <JobCard background="bg-green-100">
          <h2 class="text-2xl font-bold">For Employers</h2>
          <p class="mt-2 mb-4">List your job to find the perfect developer for the role</p>
          <RouterLink
            to="/jobs/Add"
            class="inline-block bg-green-900 text-white rounded-lg px-4 py-2 hover:bg-green-600"
          >
            Add Job
          </RouterLink>
        </JobCard>
      </div>
    </div>
  </section>
</template>
