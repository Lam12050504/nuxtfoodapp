<template>
    <section class="restaurantinfo">
        <div v-for="store in datasource" :key="store.id" class="item-contain">
            <h2>{{store.name}}</h2>
            <p class="time">Delivery Time {{store.deliveryTime}}</p>
            <p class="rating">Rating: {{store.rating}}</p>
            <p v-if="store.freeDelivery" class="label">
                <span>Free Delivery</span>
            </p>
            <div class="row">
            <div
          v-for="menuitem in store.menu"
          :key="menuitem.id"
          :style="`background: url(/${menuitem.img}) no-repeat center center`"
          class="items">
                <div class="iteminfo">
                    <div>
                        <h4>{{menuitem.item}}</h4>
                        <p>{{priceFomatting(menuitem.price)}}</p>
                    </div>
                    <nuxt-link :to="`/item/${menuitem.id}`">
                        <button class="ghost"> View item</button>
                    </nuxt-link>
                </div>
            </div>
        </div>
        </div>
    </section>
</template>

<script>

    export default {
        props: {
           datasource: {
               type:[Array,Object],
           }
        },
        methods:{
            priceFomatting (item) {
                return '$' + item.toFixed(2)
            }
    }
    }
</script>
<style lang="scss" scoped>

</style>