<template>
  <section class="education-section">
    <AppContainer>
      <div class="education-section__content">
        <div class="education-section__text">
          <span class="education-section__sub--title">Team</span>
          <h2 class="education-section__title">Education Program</h2>
          <p class="education-section__description">
            Problems trying to resolve the conflict between <br />
            the two major realms of Classical physics: Newtonian mechanics
          </p>
          <ProfileCardCarousel />
        </div>
      </div>
    </AppContainer>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ProfileCardCarousel from './UI/ProfileCardCarousel.vue'
import AppContainer from './UI/AppContainer.vue'

export default defineComponent({
  name: 'EducationSection',
  components: {
    ProfileCardCarousel,
    AppContainer,
  },
})
</script>

<style scoped lang="scss">
.education-section {
  background-color: #fff;
  padding: 8rem 0;

  .container {
    gap: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__content {
    width: 100%;
  }

  &__sub--title {
    display: block;
    font-weight: 700;
    font-size: 14px;
    margin-bottom: 1rem;
    color: #96bb7c;
  }

  &__title {
    font-weight: 700;
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: #252b42;
  }

  &__description {
    font-size: 14px;
    color: #737373;
    margin-bottom: 4rem;
    font-weight: 400;
  }
}
</style>
