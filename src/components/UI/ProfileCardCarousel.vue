<template>
  <swiper
    :slidesPerView="1"
    :spaceBetween="50"
    :loop="true"
    :autoplay="{
      delay: 2500,
      disableOnInteraction: false,
    }"
    :modules="modules"
    :breakpoints="{
      '576': {
        slidesPerView: 2,
        spaceBetween: 20,
      },

      '992': {
        slidesPerView: 3,
        spaceBetween: 20,
      },
      '1200': {
        slidesPerView: 4,
        spaceBetween: 50,
      },
    }"
  >
    <swiper-slide v-for="(card, index) in profileCards" :key="index">
      <ProfileCard :image="card.image" :title="card.title" :description="card.description" />
    </swiper-slide>
  </swiper>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/swiper-bundle.css'
import ProfileCard from './ProfileCard.vue'
import userCover1 from '@/assets/user-cover-1.png'
import userCover2 from '@/assets/user-cover-2.png'
import userCover3 from '@/assets/user-cover-3.png'
import userCover4 from '@/assets/user-cover-4.png'

// Import Swiper styles
import 'swiper/css'
import { Autoplay } from 'swiper/modules'

export default defineComponent({
  name: 'ProfileCardCarousel',
  components: {
    Swiper,
    SwiperSlide,
    ProfileCard,
  },
  setup() {
    return {
      modules: [Autoplay],
    }
  },
  data() {
    return {
      profileCards: [
        { image: userCover1, title: 'Julian Jameson', description: 'Profession' },
        { image: userCover2, title: 'Julian Jameson', description: 'Profession' },
        { image: userCover3, title: 'Julian Jameson', description: 'Profession' },
        { image: userCover4, title: 'Julian Jameson', description: 'Profession' },
        { image: userCover4, title: 'Michael Brown', description: 'Data Scientist' },
      ],
    }
  },
})
</script>

<style scoped lang="scss">
.swiper-horizontal {
  padding: 8px;
}
</style>
