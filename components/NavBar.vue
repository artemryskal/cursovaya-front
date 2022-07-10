<template>
  <nav class="nav">
    <ul class="nav__list">
      <li v-for="(link, i) in linksList" :key="i" class="nav__item">
        <NuxtLink :to="link.href" class="nav__link">
          {{ link.text }}
        </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  data () {
    return {
      linksList: [
        { text: 'Магазин', href: '/shop' },
        { text: 'Контакты', href: '/contacts' },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.nav {
  &__list {
    display: flex;
    column-gap: 2.5rem;
  }

  &__link {
    text-transform: uppercase;
    text-decoration: none;
    color: inherit;
    font-weight: 500;
    font-size: 0.875rem;
  }
}
</style>
