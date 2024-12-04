<template>
  <div class="card">
    <div class="card__icon">
      <img :src="icon" :alt="`${title} Icon`" />
    </div>
    <h3 class="card__title">{{ title }}</h3>
    <div class="card__line"></div>
    <p class="card__description">{{ description }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PackageCard',
  props: {
    icon: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },
})
</script>

<style scoped lang="scss">
.card {
  background-color: #fff;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0px 13px 19px rgba(0, 0, 0, 0.07);

  &__icon {
    background-color: #96bb7c;
    padding: 1rem;
    border-radius: 10px;
    margin-bottom: 1rem;
    display: inline-block;

    img {
      color: #fff;
      width: 32px;
      height: 32px;
    }
  }

  &__title {
    font-size: 1rem;
    font-weight: 700;
    color: #252b42;
    margin-bottom: 1rem;
  }

  &__line {
    width: 50px;
    height: 2px;
    background-color: #e74040;
    margin-bottom: 1rem;
  }

  &__description {
    font-size: 14px;
    font-weight: 400;
    color: #737373;
  }
}
</style>
