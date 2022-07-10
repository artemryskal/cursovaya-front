<template>
  <section class="form-section">
    <h2 class="form-section__heading heading heading--h3">
      Введите данные для заказа
    </h2>

    <form ref="form" class="form" @submit.prevent="submitForm">
      <label class="form__label">
        Ваше имя
        <input v-model="userData.name" type="text" class="form__input" placeholder="Например, Андрей" required>
      </label>

      <label class="form__label">
        Ваша фамилия
        <input v-model="userData.last_name" type="text" class="form__input" placeholder="Например, Кулебяков" required>
      </label>

      <label class="form__label">
        Ваш номер телефона
        <input v-model="userData.phone" type="text" class="form__input" placeholder="+7 (900) 000-00-00" required>
      </label>

      <label class="form__label">
        Ваш email
        <input v-model="userData.email" type="text" class="form__input" placeholder="example@example.com" required>
      </label>

      <label class="form__label">
        Ваш адрес проживания
        <input v-model="userData.address" type="text" class="form__input" placeholder="Москва, Красная Площадь, дом 2, п. 1, этаж 21, кв. 181" required>
      </label>

      <input type="submit" value="Заказать" class="btn btn--primary">
    </form>
  </section>
</template>

<script>
export default {
  name: 'CartForm',
  data () {
    return {
      userData: {
        name: '',
        last_name: '',
        phone: '',
        email: '',
        address: '',
      }
    }
  },
  methods: {
    async submitForm () {
      try {
        await this.$axios
          .post('requests/', this.userData)
          .then((res) => {
            this.$toast.success('Заявка успешно принята! Ожидайте доставки товара')
            this.$refs.form.reset()
            localStorage.clear()
            this.$router.push({ path: '/shop' })
          })
      } catch (e) {
        this.$toast.error('Неизвестная ошибка. Не удалось обработать запрос')
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@use '@/assets/scss/components/form.scss';

.form-section {
  margin-top: 1rem;
  margin-bottom: 1rem;

  &__heading {
    margin-bottom: 1rem;
  }
}
</style>
