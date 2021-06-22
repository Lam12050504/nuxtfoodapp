<template>
  <main class="container restaurant">
      <AppHead />
      <AppRestaurantInf :datasource="fooddata" />
  </main>
</template>

<script>
import AppHead from '../components/AppHead.vue';
import AppRestaurantInf from '../components/AppRestaurantInf.vue';
import {mapState} from "vuex";
export default {
  components: {
    AppHead,
    AppRestaurantInf
  },
  computed:{
    ...mapState(['fooddata'])
    }
}
</script>

<style>

</style>
