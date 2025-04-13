<script lang="ts" setup>
import NavBarSection from '@/components/NavbarSection.vue'
import HeroSection from '@/components/HeroSection.vue'
import HomeCards from '@/components/HomeCards.vue'
import JobListings from '@/components/JobListings.vue'
</script>

<template>
  <NavBarSection />
  <HeroSection />
  <HomeCards />
  <JobListings :limit="3" :show-view-more="true" />
</template>
