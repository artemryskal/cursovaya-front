<template>
  <ul class="partners container">
    <li v-for="(partner, i) in partnersList" :key="i" class="partners__item">
      <img :src="require(`@/assets/images/${partner.toLowerCase()}.png`)" :alt="partner">
    </li>
  </ul>
</template>

<script>
export default {
  name: 'PartnersList',
  data () {
    return {
      partnersList: [
        'Sunshine', 'Pure', 'Automotive', 'Hand Crafted'
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.partners {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
  padding: 4% 3%;
  box-shadow: 0px 100px 80px rgba(174, 174, 174, 0.08), 0px 43.751px 36.4414px rgba(174, 174, 174, 0.0575083), 0px 19.8401px 19.1406px rgba(174, 174, 174, 0.0476886), 0px 6.77214px 9.61331px rgba(174, 174, 174, 0.04), 0px 0.190079px 4.14347px rgba(174, 174, 174, 0.0323114), 0px -1.73968px 1.20532px rgba(174, 174, 174, 0.0224916);

  @media screen and (max-width: 719px) {
    justify-content: center;
  }
}
</style>
