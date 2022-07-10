<template>
  <main class="shop container">
    <h1 class="heading heading--h2">
      Страница магазина
    </h1>

    <ProductsList :list="productsList" />
  </main>
</template>

<script>
export default {
  name: 'ShopPage',
  data () {
    return {
      productsList: []
    }
  },
  async fetch () {
    const response = await fetch('http://127.0.0.1:8000/api/products')
    this.productsList = await response.json()
  },
  head () {
    return {
      title: 'Магазин'
    }
  },
}
</script>

<style scoped>
</style>
