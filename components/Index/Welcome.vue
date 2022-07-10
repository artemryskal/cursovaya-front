<template>
  <section class="welcome container">
    <div class="welcome__main">
      <h1 class="heading heading--h1">
        <mark class="mark">
          Захватывающее место
        </mark>
        для всей семьи, чтобы делать покупки.
      </h1>
      <nuxt-link to="/shop" class="welcome__btn btn btn--primary">
        Перейти в магазин
      </nuxt-link>
    </div>

    <img src="@/assets/images/welcome.png" alt="VR-очки" class="welcome__image">
  </section>
</template>

<script>
export default {
  name: 'IndexWelcome'
}
</script>

<style lang="scss" scoped>
.welcome {
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  column-gap: 1.75rem;
  align-items: center;
  margin-top: 4.7%;
  overflow-x: hidden;

  &__main {
    display: flex;
    flex-direction: column;
    row-gap: 1.8rem;
  }

  &__btn {
    width: fit-content;
  }

  @media screen and (max-width: 580px) {
    grid-template-columns: 1fr;

    &__image {
      display: none;
    }
  }
}
</style>
