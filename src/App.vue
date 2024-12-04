<template>
  <div>
    <AppHeader />
    <HeroSection />
    <PackagesSection />
    <EducationSection />
    <NewsletterSection />
    <FooterSection />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppHeader from './components/AppHeader.vue'
import HeroSection from './components/HeroSection.vue'
import PackagesSection from './components/PackagesSection.vue'
import EducationSection from './components/EducationSection.vue'
import NewsletterSection from './components/NewsletterSection.vue'
import FooterSection from './components/FooterSection.vue'

export default defineComponent({
  components: {
    AppHeader,
    HeroSection,
    PackagesSection,
    EducationSection,
    NewsletterSection,
    FooterSection,
  },
})
</script>
