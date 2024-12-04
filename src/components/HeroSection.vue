<template>
  <section class="hero">
    <AppContainer>
      <div class="hero__content">
        <p class="hero__welcome">Welcome</p>
        <h1 class="hero__title">Best Learning Opportunities</h1>
        <p class="hero__subtitle">Our goal is to make online education work for everyone</p>
        <div class="hero__actions">
          <AppButton variant="filled">Join Us</AppButton>
          <AppButton variant="outlined">Learn More</AppButton>
        </div>
      </div>
      <div class="hero__image">
        <img src="@/assets/hero-cover-1.png" alt="Hero Cover" />
      </div>
    </AppContainer>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppButton from './UI/AppButton.vue'
import AppContainer from './UI/AppContainer.vue'

export default defineComponent({
  name: 'HeroSection',
  components: {
    AppButton,
    AppContainer,
  },
})
</script>

<style scoped lang="scss">
.hero {
  background-color: #fff2f3;
  padding: 8rem 0;
  position: relative;

  .container {
    gap: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__content {
    max-width: 50%;
  }

  &__welcome {
    color: #96bb7c;
    font-weight: 700;
    margin-bottom: 16px;
  }

  &__title {
    font-size: 58px;
    font-weight: 700;
    color: #252b42;
    margin-bottom: 1rem;
  }

  &__subtitle {
    font-weight: 400;
    font-size: 1.25rem;
    color: #737373;
    margin-bottom: 2rem;
  }

  &__actions {
    display: flex;
    gap: 0.5rem;

    .button {
      padding: 15px 40px;
    }
  }

  &__image {
    position: absolute;
    bottom: 0;
    right: 0;
    max-width: 45%;
    img {
      max-width: 100%;
      height: auto;
      display: block;
    }
  }
}

@media (max-width: 992px) {
  .hero {
    padding: 4rem 1rem;

    &__content {
      text-align: center;
      margin: 0 auto;
      max-width: 80%;
    }

    &__title {
      font-size: 40px;
    }

    &__subtitle {
      font-size: 1rem;
    }

    &__actions {
      justify-content: center;
      flex-direction: column;
      max-width: 70%;
      margin: 0 auto;
    }

    &__actions button {
      margin: 0.5rem 0;
    }

    &__image {
      display: none;
    }
  }
}

@media (max-width: 576px) {
  .hero__title {
    font-size: 28px;
  }

  .hero__actions {
    max-width: 90%;
  }

  .hero__subtitle {
    font-size: 0.9rem;
  }
}
</style>
