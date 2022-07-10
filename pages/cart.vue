<template>
  <section class="cart container">
    <h1 class="heading heading--h2">
      Корзина
    </h1>

    <div v-if="products.length">
      <ProductsList :list="products"/>
      <CartForm />
    </div>
    <p v-else class="cart__empty">
      Нет добавленных товаров в корзину
    </p>
  </section>
</template>

<script>
export default {
  name: 'CartPage',
  data () {
    return {
      products: []
    }
  },
  mounted () {
    Object.keys(localStorage).forEach(async (key) => {
      const response = await fetch(`http://127.0.0.1:8000/api/products/${key}`)
      const json = await response.json()

      this.products.push(json)
    })
  }
}
</script>

<style scoped>

</style>
