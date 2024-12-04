<template>
  <footer class="footer-section">
    <AppContainer>
      <div class="footer-columns">
        <FooterColumn
          title="Company Info"
          :items="[
            { name: 'About Us', link: '#' },
            { name: 'Carrier', link: '#' },
            { name: 'We are hiring', link: '#' },
            { name: 'Blog', link: '#' },
          ]"
        />

        <FooterColumn
          title="Legal"
          :items="[
            { name: 'About Us', link: '#' },
            { name: 'Carrier', link: '#' },
            { name: 'We are hiring', link: '#' },
            { name: 'Blog', link: '#' },
          ]"
        />

        <FooterColumn
          title="Features"
          :items="[
            { name: 'Business Marketing', link: '#' },
            { name: 'User Analytic', link: '#' },
            { name: 'Live Chat', link: '#' },
            { name: 'Unlimited Support', link: '#' },
          ]"
        />

        <FooterColumn
          title="Resources"
          :items="[
            { name: 'IOS & Android', link: '#' },
            { name: 'Watch a Demo', link: '#' },
            { name: 'Customers', link: '#' },
            { name: 'API', link: '#' },
          ]"
        />

        <FooterContact />
      </div>
    </AppContainer>
    <FooterNote />
  </footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import AppContainer from './UI/AppContainer.vue'
import FooterColumn from './UI/FooterColumn.vue'
import FooterContact from './UI/FooterContact.vue'
import FooterNote from './UI/FooterNote.vue'

export default defineComponent({
  name: 'FooterSection',
  components: {
    AppContainer,
    FooterColumn,
    FooterContact,
    FooterNote,
  },
})
</script>

<style scoped lang="scss">
.footer-section {
  background-color: #fff;
  .container {
    padding: 4rem 0;
  }

  .footer-columns {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 2rem;

    @media (max-width: 1024px) {
      grid-template-columns: repeat(3, 1fr);
    }

    @media (max-width: 768px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media (max-width: 480px) {
      grid-template-columns: 1fr;
    }
  }
}
</style>
