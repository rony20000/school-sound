<template>
  <div class="footer-column">
    <h4 class="footer-column__title">{{ title }}</h4>
    <ul class="footer-column__list">
      <li v-for="item in items" :key="item.name">
        <AppLink :href="item.link">{{ item.name }}</AppLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import AppLink from './AppLink.vue'

export default defineComponent({
  name: 'FooterColumn',
  components: {
    AppLink,
  },
  props: {
    title: String,
    items: {
      type: Array as PropType<Array<{ name: string; link: string }>>,
      required: true,
    },
  },
})
</script>

<style scoped lang="scss">
.footer-column {
  &__title {
    font-size: 1rem;
    font-weight: 700;
    color: #252b42;
    margin-bottom: 1rem;
  }

  .app-link {
    margin-bottom: 0.5rem;
  }

  &__list {
    list-style: none;
    padding: 0;
    margin: 0;
  }
}
</style>
