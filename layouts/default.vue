<template>
  <div class="layout">
    <TheHeader class="container" />
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout'
}
</script>

<style scoped>
.layout {
  overflow-x: hidden;
  padding-bottom: 2rem;
}
</style>
