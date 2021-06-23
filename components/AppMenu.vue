<template>
  <nav>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/restaurant/Restaurant">Restaurant</nuxt-link>
      </li> 
    </ul>
    <nuxt-link to="/Cart">Cart-{{updateCount}}</nuxt-link>
  </nav>
</template>

<script>
import {mapState} from 'vuex';
import {mapGetters} from 'vuex';
export default {
  computed: {
    ...mapState(['cart','count']),
    ...mapGetters(['updateCount'])
  },
};
</script>

<style lang="scss" scoped></style>
