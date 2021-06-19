<template>
  <main class="container">
      <AppHead />
      <app-restaurant-inf />
  </main>
</template>

<script>
import AppHead from '../components/AppHead.vue';
import AppRestaurantInf from '../components/AppRestaurantInf.vue';
export default {
  components: {
    AppHead,
    AppRestaurantInf
  }
}
</script>

<style>

</style>
