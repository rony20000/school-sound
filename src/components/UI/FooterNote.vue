<template>
  <div class="footer-note">
    <AppContainer>
      <p class="footer-note__text">Made With Love By Figmaland All Rights Reserved</p>
      <div class="footer-note__social-icons">
        <a href="#" target="_blank">
          <img :src="facebookIcon" alt="Facebook" />
        </a>
        <a href="#" target="_blank">
          <img :src="instagramIcon" alt="Instagram" />
        </a>
        <a href="#" target="_blank">
          <img :src="twitterIcon" alt="Twitter" />
        </a>
      </div>
    </AppContainer>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import facebookIcon from '@/assets/facebook.svg'
import instagramIcon from '@/assets/instagram.svg'
import twitterIcon from '@/assets/twitter.svg'
import AppContainer from './AppContainer.vue'

export default defineComponent({
  name: 'FooterNote',
  components: {
    AppContainer,
  },
  data() {
    return {
      facebookIcon,
      instagramIcon,
      twitterIcon,
    }
  },
})
</script>

<style scoped lang="scss">
.footer-note {
  padding: 2rem 0;
  background-color: #fafafa;

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    @media (max-width: 768px) {
      flex-direction: column;
      gap: 1rem;
    }
  }

  &__text {
    font-weight: 700;
    font-size: 14px;
    color: #737373;
  }

  &__social-icons {
    display: flex;
    gap: 1rem;

    a img {
      width: 24px;
      height: 24px;
    }
  }
}
</style>
