<template>
  <section class="contacts container">
    <h1 class="heading heading--h2">
      Контакты
    </h1>

    <ul class="contacts__list">
      <li class="contacts__item">
        <a href="https://t.me/southgaarden" target="_blank" class="contacts__link">
          <img src="@/assets/icons/telegram.svg" alt="Telegram" class="contacts__icon">
          Telegram
        </a>
      </li>
      <li class="contacts__item">
        <a href="tel:+79000000000" target="_blank" class="contacts__link">
          <img src="@/assets/icons/phone.svg" alt="Phone" class="contacts__icon">
          Телефон
        </a>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'ContactsPage',
  head () {
    return {
      title: 'Контакты'
    }
  }
}
</script>

<style lang="scss" scoped>
.contacts {
  &__list {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  &__item {
    font-size: 1.2rem;
    font-weight: 600;
    padding-top: 2rem;
    padding-bottom: 2rem;
    border-radius: 10px;

    &:first-of-type {
      background-color: #0088cc;
    }

    &:last-of-type {
      background-color: #0a560a;
    }
  }

  &__link {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    color: #fff;
    text-decoration: none;
  }

  &__icon {
    max-width: 200px;
  }

  @media screen and (max-width: 649px) {
    &__list {
      grid-template-columns: 1fr;
    }
  }
}
</style>
