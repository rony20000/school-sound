<template>
  <a :href="href" class="app-link" :style="{ color }" v-bind="{ ...attributes }">
    <span class="app-link__text"><slot></slot></span>
    <img v-if="icon" :src="icon" class="app-link__icon" />
  </a>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AppLink',
  props: {
    href: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      default: '#737373',
    },
    icon: {
      type: String,
      default: '',
    },
    attributes: {
      type: Object,
      default: () => ({}),
    },
  },
})
</script>

<style scoped lang="scss">
.app-link {
  display: inline-flex;
  align-items: center;
  text-decoration: none;
  transition: color 0.3s ease;

  &__text {
    font-size: 14px;
    font-weight: 700;
    transition: color 0.3s ease;

    &:hover {
      color: #96bb7c;
    }
  }

  &__icon {
    margin-left: 0.5rem;
    display: inline-block;
    transition: transform 0.3s ease;
    width: 20px;
  }

  &:hover .app-link__icon {
    transform: translateX(5px); /* Move icon to the right on hover */
  }
}
</style>
