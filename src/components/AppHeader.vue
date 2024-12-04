<template>
  <header class="app-header">
    <AppContainer>
      <div class="app-header__logo">Brandname</div>

      <button class="app-header__hamburger" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <nav class="app-header__nav" :class="{ 'is-open': isMenuOpen }">
        <button class="app-header__close" @click="toggleMenu">✖</button>

        <ul>
          <li><AppLink href="#home" @click="closeMenu">Home</AppLink></li>
          <li><AppLink href="#product" @click="closeMenu">Product</AppLink></li>
          <li><AppLink href="#pricing" @click="closeMenu">Pricing</AppLink></li>
          <li><AppLink href="#contact" @click="closeMenu">Contact</AppLink></li>
        </ul>
      </nav>

      <nav class="app-header__nav--desktop">
        <ul>
          <li><AppLink href="#home">Home</AppLink></li>
          <li><AppLink href="#product">Product</AppLink></li>
          <li><AppLink href="#pricing">Pricing</AppLink></li>
          <li><AppLink href="#contact">Contact</AppLink></li>
        </ul>
      </nav>

      <div class="app-header__actions">
        <AppLink href="#login" color="#96BB7C">Login</AppLink>
        <AppButton variant="filled" icon="→" @click="joinUs">JOIN US</AppButton>
      </div>
    </AppContainer>
  </header>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import AppLink from './UI/AppLink.vue'
import AppButton from './UI/AppButton.vue'
import AppContainer from './UI/AppContainer.vue'

export default defineComponent({
  name: 'AppHeader',
  components: {
    AppLink,
    AppButton,
    AppContainer,
  },
  setup() {
    const isMenuOpen = ref(false)

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value
    }

    const closeMenu = () => {
      isMenuOpen.value = false
    }

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
    }
  },
  methods: {
    joinUs() {
      alert('Join Us button clicked!')
    },
  },
})
</script>

<style scoped lang="scss">
.app-header {
  background-color: #fff2f3;

  .container {
    padding: 1rem 6rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__logo {
    font-size: 24px;
    font-weight: 700;
    color: #252b42;
  }

  &__nav {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: 100vh;
    background-color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transform: translateY(-100%);
    transition:
      transform 0.3s ease-in-out,
      visibility 0.3s ease-in-out;
    visibility: hidden;
    z-index: 1000;

    &.is-open {
      transform: translateY(0);
      visibility: visible;
    }

    &:not(.is-open) {
      visibility: hidden;
      transform: translateY(-100%);
    }

    .close-menu {
      position: absolute;
      top: 1rem;
      right: 1rem;
      background: none;
      border: none;
      font-size: 2rem;
      color: #333;
      cursor: pointer;
    }

    ul {
      list-style: none;
      padding: 0;
      margin: 2rem 0;
      display: flex;
      flex-direction: column;
      gap: 1rem;

      li {
        text-align: center;
      }
    }

    &__close {
      position: absolute;
      top: 1rem;
      right: 1rem;
      background: none;
      border: none;
      font-size: 2rem;
      color: #252b42;
      cursor: pointer;
    }
  }

  &__nav--desktop {
    ul {
      display: flex;
      gap: 1rem;
      list-style: none;
    }
  }

  &__actions {
    display: flex;
    align-items: center;
    gap: 2rem;
  }

  .app-header__hamburger {
    display: none;
    background: none;
    border: none;
    flex-direction: column;
    gap: 0.3rem;
    cursor: pointer;

    span {
      display: block;
      width: 25px;
      height: 3px;
      background-color: #252b42;
    }
  }

  @media (max-width: 1200px) {
    .container {
      padding: 1rem 0;
    }
  }

  @media (max-width: 992px) {
    .app-header__nav--desktop {
      display: none;
    }

    .app-header__hamburger {
      display: flex;
    }

    .app-header__actions {
      display: none;
    }

    .app-header__nav {
      display: flex;
    }
  }
}
</style>
