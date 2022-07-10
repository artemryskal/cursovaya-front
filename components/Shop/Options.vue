<template>
  <ul class="options">
    <li class="options__item">
      <form @submit.prevent>
        <label for="name" class="visually-hidden">
          Название товара
        </label>
        <input id="name" type="text" placeholder="Введите название" class="form__input">
        <input type="submit" value="Поиск" class="visually-hidden">
      </form>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'ShopOptions'
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/components/form.scss';
</style>
