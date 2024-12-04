<template>
  <div class="profile-card">
    <div class="profile-card__image">
      <img :src="image" alt="Profile" />
    </div>
    <div class="profile-card__content">
      <h3 class="profile-card__title">{{ title }}</h3>
      <p class="profile-card__description">{{ description }}</p>
      <div class="profile-card__socials">
        <a href="https://facebook.com/in/johndoe" target="_blank" class="profile-card__social-icon">
          <img :src="facebookIcon" alt="facebook" />
        </a>
        <a
          href="https://instagram.com/in/johndoe"
          target="_blank"
          class="profile-card__social-icon"
        >
          <img :src="instagramIcon" alt="instagram" />
        </a>
        <a href="https://twutter.com/in/johndoe" target="_blank" class="profile-card__social-icon">
          <img :src="twitterIcon" alt="twutter" />
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import facebookIcon from '@/assets/facebook.svg'
import instagramIcon from '@/assets/instagram.svg'
import twitterIcon from '@/assets/twitter.svg'

export default {
  name: 'ProfileCard',
  props: {
    title: String,
    description: String,
    image: String,
  },
  data() {
    return {
      facebookIcon,
      instagramIcon,
      twitterIcon,
    }
  },
}
</script>

<style scoped lang="scss">
.profile-card {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;

  &__image {
    width: 100%;
    height: 230px;
    overflow: hidden;
  }

  &__image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  &__content {
    padding: 2rem;
    text-align: center;
  }

  &__title {
    font-size: 1rem;
    font-weight: 700;
    color: #252b42;
    margin-bottom: 0.5rem;
  }

  &__description {
    font-weight: 400;
    font-size: 12px;
    color: #737373;
    margin-bottom: 1rem;
  }

  &__socials {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
  }
}
</style>
