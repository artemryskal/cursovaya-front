<template>
  <nav class="nav">
    <button ref="btn" class="nav__btn btn btn--primary" aria-expanded="false" aria-controls="nav-list" @click.stop="toggleNav">
      <svg width="32" height="32" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
        <defs><style>.cls-1{fill:none;}</style></defs><title/>
        <g id="Layer_2" data-name="Layer 2">
          <path class="path" d="M28,10H4A1,1,0,0,1,4,8H28a1,1,0,0,1,0,2Z"/>
          <path class="path" d="M28,17H4a1,1,0,0,1,0-2H28a1,1,0,0,1,0,2Z"/>
          <path class="path" d="M28,24H4a1,1,0,0,1,0-2H28a1,1,0,0,1,0,2Z"/>
        </g>
        <g id="frame"><rect class="cls-1" height="32" width="32"/></g>
      </svg>
    </button>

    <ul ref="nav" class="nav__list" aria-controls="nav-list">
      <li v-for="(link, i) in linksList" :key="i" class="nav__item" @click="toggleNav">
        <NuxtLink :to="link.href" class="nav__link">
          {{ link.text }}
        </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'TheHeaderNav',
  data () {
    return {
      linksList: [
        { text: 'Магазин', href: '/shop' },
        { text: 'Контакты', href: '/contacts' },
        { text: 'Корзина', href: '/cart' },
      ]
    }
  },
  methods: {
    toggleNav () {
      const expanded = this.$refs.btn.getAttribute('aria-expanded') === 'true'
      document.body.classList.toggle('fixed')
      this.$refs.btn.classList.toggle('active')
      this.$refs.btn.setAttribute('aria-expanded', !expanded)
      this.$refs.nav.classList.toggle('active')
    }
  }
}
</script>

<style lang="scss" scoped>
.nav {
  &__list {
    position: fixed;
    top: 0;
    bottom: 0;
    width: 100%;
    right: -100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 2rem;
    background-color: var(--secondary);
    transition: right 0.4s;

    &.active {
      right: 0;
    }
  }

  &__btn {
    position: relative;
    min-width: fit-content;
    padding: 0;
    background: none;
    z-index: 2;
  }

  .path {
    transition: transform 0.1s;
  }

  &__btn.active .path {
    &:first-of-type {
      transform: translate(10px, 0px) rotate(45deg);
    }

    &:nth-of-type(2) {
      transform: translateX(-100%);
    }

    &:last-of-type {
      transform: translate(-12px, 13px) rotate(-45deg);
    }
  }

  &__link {
    text-transform: uppercase;
    text-decoration: none;
    color: inherit;
    font-size: 1.5rem;
    font-weight: 600;
  }
}
</style>
