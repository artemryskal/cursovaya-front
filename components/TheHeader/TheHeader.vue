<template>
  <header class="header container">
    <div class="header__pc">
      <NuxtLink to="/">
        <img src="@/assets/icons/logo.svg" alt="Logo">
      </NuxtLink>

      <NavBar />

      <TheHeaderMenu />
    </div>

    <div class="header__mobile">
      <NuxtLink to="/">
        <img src="@/assets/icons/logo.svg" alt="Logo">
      </NuxtLink>

      <TheHeaderNav />
    </div>
  </header>
</template>

<script>
export default {
  name: 'TheHeader'
}
</script>

<style lang="scss" scoped>
.header {
  padding-top: 1.6rem;
  padding-bottom: 1.6rem;

  &__pc,
  &__mobile {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__mobile {
    display: none;
  }

  @media screen and (max-width: 600px) {
    &__pc {
      display: none;
    }

    &__mobile {
      display: flex;
    }
  }
}
</style>
