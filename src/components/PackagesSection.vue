<template>
  <section class="packages">
    <AppContainer>
      <div class="packages__content">
        <div class="packages__line"></div>
        <h2 class="packages__title">Approachable Packages</h2>
        <p class="packages__description">
          Problems trying to resolve the conflict between the two major realms of Classical physics:
          Newtonian mechanics
        </p>
        <AppLink href="#learn-more" color="#96BB7C" :icon="arrow">Learn More</AppLink>
      </div>

      <div class="packages__cards">
        <PackageCard
          :icon="BlackboardsIcon"
          title="Certified Teacher"
          description="The gradual accumulation of information about"
        />
        <PackageCard
          :icon="TelescopeIcon"
          title="Expert Instruction"
          description="The gradual accumulation of information about"
        />
      </div>
    </AppContainer>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppLink from './UI/AppLink.vue'
import AppContainer from './UI/AppContainer.vue'
import PackageCard from './UI/PackageCard.vue'
import BlackboardsIcon from '@/assets/blackboards.svg'
import TelescopeIcon from '@/assets/telescope.svg'
import arrow from '@/assets/arrow.svg'

export default defineComponent({
  name: 'PackagesSection',
  components: {
    AppLink,
    AppContainer,
    PackageCard,
  },
  setup() {
    return {
      BlackboardsIcon,
      TelescopeIcon,
      arrow,
    }
  },
})
</script>

<style scoped lang="scss">
.packages {
  padding: 8rem 0;
  background-color: #fff;

  .container {
    gap: 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__line {
    width: 94px;
    height: 7px;
    background-color: #e74040;
    margin-bottom: 2rem;
  }

  &__content {
    max-width: 50%;
  }

  &__title {
    font-size: 2.5rem;
    font-weight: 700;
    color: #252b42;
    margin-bottom: 2rem;
  }

  &__description {
    font-size: 14px;
    color: #718096;
    font-weight: 400;
    margin-bottom: 2rem;
  }

  &__cards {
    display: flex;
    gap: 2rem;
    max-width: 50%;
  }

  @media (max-width: 992px) {
    .container {
      flex-direction: column;
    }

    &__content {
      margin-bottom: 2rem;
    }

    &__content,
    &__cards {
      max-width: 100%;
    }

    &__cards {
      flex-direction: column;
    }
  }
}
</style>
