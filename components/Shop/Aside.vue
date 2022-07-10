<template>
  <aside class="aside">
    <h2 class="aside__heading heading--h3">
      Параметры оторбажения
    </h2>

    <ShopOptions />
  </aside>
</template>

<script>
export default {
  name: 'ShopAside',
}
</script>

<style lang="scss" scoped>
.aside {
  background-color: var(--secondary);
  color: var(--primary);
  padding: 1rem;

  &__heading {
    margin-bottom: 0.5rem;
  }
}
</style>
