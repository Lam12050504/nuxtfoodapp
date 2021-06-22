<template>
    <main class="container restaurant">
        <div class="restaurantheading">
            <h1>Restaurant</h1>
            
            <AppSelect  @change="selectRestaurant = $event"/>
        </div>
        <AppRestaurantInf :datasource="filterData" />
    </main>
</template>

<script>
import AppRestaurantInf from '~/components/AppRestaurantInf.vue'
import AppSelect from '~/components/AppSelect.vue'
import {mapState} from "vuex";
export default {
   components: {
       AppRestaurantInf,
       AppSelect
   },
   data() {
       return {
           selectRestaurant: '',
       }
   },
   computed: {
       ...mapState(['fooddata']),
       filterData() {
           if(this.selectRestaurant){
               return this.fooddata.filter((el) => {
                   let name = el.name.toLowerCase()
                   return name.includes(this.selectRestaurant);
               });
           }
           return this.fooddata
       }
   }
}
</script>

<style lang="scss" scoped>

</style>