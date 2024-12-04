<template>
  <div class="footer-contact">
    <h4 class="footer-contact__title">Get In Touch</h4>
    <ul class="footer-contact__list">
      <li>
        <img :src="contact" alt="Phone" class="footer-contact__icon" />
        <span>(480) 555-0103</span>
      </li>
      <li>
        <img :src="location" alt="Location" class="footer-contact__icon" />
        <span>4517 Washington Ave. Manchester, Kentucky 39495</span>
      </li>
      <li>
        <img :src="email" alt="Email" class="footer-contact__icon" />
        <span>debra.holt@example.com</span>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import contact from '@/assets/contact.svg'
import email from '@/assets/email.svg'
import location from '@/assets/location.svg'

export default defineComponent({
  name: 'FooterContact',
  data() {
    return {
      contact,
      email,
      location,
    }
  },
})
</script>

<style scoped lang="scss">
.footer-contact {
  &__title {
    font-size: 1rem;
    font-weight: 700;
    color: #252b42;
    margin-bottom: 1rem;
  }

  &__list {
    list-style: none;
    padding: 0;
    margin: 0;

    li {
      display: flex;
      align-items: center;
      margin-bottom: 0.75rem;

      .footer-contact__icon {
        color: #96bb7c;
        width: 1.5rem;
        height: 1.5rem;
        margin-right: 0.5rem;
      }

      span {
        font-size: 14px;
        font-weight: 700;
        color: #737373;
      }
    }
  }
}
</style>
