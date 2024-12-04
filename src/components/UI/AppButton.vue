<template>
  <button
    class="button"
    :class="[
      variant === 'filled' ? 'button--filled' : 'button--outlined',
      { 'button--with-icon': icon },
    ]"
    @click="$emit('click')"
  >
    <span class="button__content">
      <slot></slot>
    </span>
    <span v-if="icon" class="button__icon">{{ icon }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'

export default defineComponent({
  name: 'AppButton',
  props: {
    variant: {
      type: String as PropType<'filled' | 'outlined'>,
      default: 'filled',
    },
    icon: {
      type: String,
      default: '',
    },
  },
})
</script>

<style scoped lang="scss">
.button {
  padding: 15px 25px;
  border-radius: 5px;
  font-size: 14px;
  font-weight: 700;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;

  &--filled {
    background-color: #96bb7c;
    color: #fff;
    border: none;

    &:hover {
      background-color: #afda90;
    }
  }

  &--outlined {
    background-color: transparent;
    color: #96bb7c;
    border: 2px solid #96bb7c;

    &:hover {
      background-color: #96bb7c;
      color: #fff;
    }
  }

  &--with-icon {
    gap: 1rem;
  }

  .button__content {
    font-weight: 700;
    font-size: 14px;
  }

  .button__icon {
    font-size: 1rem;
  }
}
</style>
