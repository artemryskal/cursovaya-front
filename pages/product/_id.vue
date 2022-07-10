<template>
  <section class="product container">
    <img :src="product.picture" alt="Изображение товара" class="product__image">
    <h1 class="heading heading--h2">
      {{ product.name }}
    </h1>
    <div class="product__rate">
      <template v-for="(rate, index) in product.rate">
        <img :key="index" src="@/assets/icons/star.svg" alt="star">
      </template>
    </div>
    <p class="product__price">
      {{ product.price }}₽
    </p>
    <p class="product__description">
      {{ product.description }}
    </p>

    <button v-if="isActiveBtn" class="product__btn btn btn--primary" @click="addToCart">
      Добавить в корзину
    </button>
    <button v-else class="product__btn btn btn--primary" disabled>
      Товар уже в корзине
    </button>
  </section>
</template>

<script>
export default {
  name: 'ProductPage',
  async asyncData ({ route }) {
    const response = await fetch(`http://127.0.0.1:8000/api/products/${route.params.id}`)
    const product = await response.json()

    return { product }
  },
  data () {
    return {
      isActiveBtn: true
    }
  },
  head () {
    return {
      title: this.product.name
    }
  },
  mounted () {
    const id = this.$route.params.id
    const disableBtn = this.disableBtn

    Object.keys(localStorage).forEach(function (key) {
      if (id === key) {
        disableBtn()
      }
    })
  },
  methods: {
    addToCart () {
      localStorage.setItem(this.product.id, this.product.id)
      this.disableBtn()
    },
    disableBtn () {
      this.isActiveBtn = false
    }
  }
}
</script>

<style lang="scss" scoped>
.product {
  &__image {
    float: left;
    max-width: 512px;
  }

  &__rate {
    margin-bottom: 0.5rem;
  }

  &__price {
    margin-bottom: 0.5rem;
    font-size: 1.2rem;
    font-weight: 600;
  }

  &__description {
    line-height: 1.2rem;
    color: #686E73;
  }

  &__btn {
    display: block;
    margin-top: 2rem;
    width: 100%;
  }

  @media screen and (max-width: 768px) {
    display: flex;
    flex-direction: column;
    gap: 1rem;

    &__image {
      float: none;
      margin: 0 auto;
      max-width: 100%;
    }
  }
}
</style>
