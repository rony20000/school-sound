<template>
  <section class="newsletter-section">
    <AppContainer>
      <div class="newsletter-content">
        <h3 class="newsletter-title">Newsletter</h3>
        <h2 class="newsletter-heading">Watch our Courses</h2>
        <p class="newsletter-description">
          Problems trying to resolve the conflict between <br />
          the two major realms of Classical physics: Newtonian mechanics
        </p>
      </div>
      <form @submit.prevent="handleSubmit" class="newsletter-form">
        <div class="input-group">
          <input type="email" v-model="email" placeholder="Your Email" class="newsletter-input" />
          <AppButton variant="filled">JOIN US</AppButton>
        </div>
        <p v-if="error" class="error-message">{{ error }}</p>
      </form>
    </AppContainer>
  </section>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import AppContainer from './UI/AppContainer.vue'
import AppButton from './UI/AppButton.vue'

export default defineComponent({
  name: 'NewsletterSection',
  components: {
    AppContainer,
    AppButton,
  },
  setup() {
    const email = ref('')
    const error = ref('')

    const validateEmail = (email: string) => {
      const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      return regex.test(email)
    }

    const handleSubmit = () => {
      if (!validateEmail(email.value)) {
        error.value = 'Please enter a valid email address.'
      } else {
        error.value = ''
        alert('Subscribed successfully!')
        email.value = ''
      }
    }

    return { email, error, handleSubmit }
  },
})
</script>

<style scoped lang="scss">
.newsletter-section {
  text-align: center;
  background-color: #fff2f3;
  padding: 8rem 0;

  @media (max-width: 768px) {
    padding: 4rem 0;
  }

  .button--filled {
    border-radius: 0;
  }

  .newsletter-content {
    margin-bottom: 5rem;

    .newsletter-title {
      font-weight: 700;
      font-size: 14px;
      color: #96bb7c;
      margin-bottom: 0.5rem;
    }

    .newsletter-heading {
      font-size: 1.5rem;
      font-weight: 700;
      color: #252b42;
      margin-bottom: 0.5rem;
    }

    .newsletter-description {
      font-weight: 400;
      font-size: 14px;
      color: #737373;
      margin-bottom: 1.5rem;
    }
  }

  .newsletter-form {
    .input-group {
      display: flex;
      max-width: 700px;
      margin: 0 auto;
      border: 1px solid #e6e6e6;
      border-radius: 5px;
      overflow: hidden;

      .newsletter-input {
        flex: 1;
        padding: 0.75rem;
        font-size: 1rem;
        border: none;
        outline: none;
        background-color: #f9f9f9;

        @media (max-width: 768px) {
          max-width: 60%;
        }

        &::placeholder {
          color: #737373;
          font-size: 14px;
          font-weight: 400;
        }
      }

      .button--filled {
        @media (max-width: 768px) {
          margin-left: auto;
          width: 40%;
        }
      }
    }

    .error-message {
      color: red;
      font-size: 0.875rem;
      margin-top: 0.5rem;
    }
  }
}
</style>
