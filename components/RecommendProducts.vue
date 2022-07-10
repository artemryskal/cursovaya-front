<template>
  <section class="popular section container">
    <h2 class="heading heading--h2 mark">
      Рекомендуемые товары
    </h2>

    <ProductsList :list="productsList" />

    <NuxtLink to="/shop" class="section__link">
      Просмотреть ещё
      <img src="@/assets/icons/arrow.svg" alt="arrow">
    </NuxtLink>
  </section>
</template>

<script>
export default {
  name: 'RecommendProducts',
  data () {
    return {
      productsList: []
    }
  },
  async fetch () {
    const response = await fetch('http://127.0.0.1:8000/api/popular')
    const json = await response.json()
    this.productsList = json
  }
}
</script>

<style lang="scss" scoped>
@use '@/assets/scss/components/products.scss';
</style>
