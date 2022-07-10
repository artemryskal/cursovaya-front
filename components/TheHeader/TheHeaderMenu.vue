<template>
  <menu class="menu">
    <ul class="menu__list">
      <li class="menu__item">
        <NuxtLink to="/cart" class="btn menu__btn">
          <img src="@/assets/icons/basket.svg" alt="Корзина">
        </NuxtLink>
      </li>
    </ul>
  </menu>
</template>

<script>
export default {
  name: 'TheHeaderMenu'
}
</script>

<style lang="scss" scoped>
.menu {
  &__list {
    display: flex;
    align-items: center;
    column-gap: 1.5rem;
  }

  &__item {
    background-color: var(--secondary);
    border-radius: 50%;
  }

  &__btn {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0.625rem;
  }
}
</style>
