<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AppContainer',
})
</script>

<style scoped lang="scss">
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
  @media (max-width: 1200px) {
    max-width: 900px;
  }

  @media (max-width: 992px) {
    max-width: 750px;
    padding: 0 0.75rem;
  }

  @media (max-width: 768px) {
    max-width: 80%;
    padding: 0 0.5rem;
  }
}
</style>
