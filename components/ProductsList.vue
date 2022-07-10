<template>
  <ul class="products">
    <li v-for="(product, i) in list" :key="i" class="products__card">
      <figure class="products__figure">
        <NuxtLink :to="`/product/${product.id}`">
          <img :src="product.picture" alt="Изображение товара" class="products__picture">
        </NuxtLink>
        <figcaption class="products__figcaption">
          <h3 class="heading heading--h3">
            {{ product.name }}
          </h3>
        </figcaption>
        <p class="products__price">
          {{ product.price }}₽
        </p>
        <p class="products__rate">
          <template v-for="(rate, index) in product.rate">
            <img :key="index" src="@/assets/icons/star.svg" alt="star">
          </template>
        </p>
      </figure>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'ProductsList',
  props: {
    list: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
@use '@/assets/scss/components/products.scss';
</style>
