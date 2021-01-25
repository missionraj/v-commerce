<template>
    <h2 class="text-center"> Featured Products </h2>
    <div class="productCard_Wrapper">
        <FeaturedProductCard v-for="product in products" :key="product.id" :details="product"/>
    </div>
</template>

<script>
import FeaturedProductCard from "@/components/FeaturedProductCard.vue";
import { ref } from 'vue';
export default {
    components : { 
        FeaturedProductCard
    },
    setup(){
        const products = ref([
            {
                id:1,
                title: 'Gym Dumbel',
                description : ' this is description ...',
                price: 400,
                img:require('@/assets/images/featured_dumbell.jpg')
            },
            {
                id:2,
                title: 'Camera ',
                description : 'this is description ...',
                price: 450,
                img:require('@/assets/images/featured_camera.jpg')
            },
            {
                id:3,
                title: 'Watch',
                description : 'this is description ...',
                price: 200,
                img:require('@/assets/images/featured_watch.jpg')
            }
        ])

        return { 
            products
        }
    }
}
</script>

<style scoped>

    .productCard_Wrapper{
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        flex-wrap: wrap;
        padding: 1rem 0;
    }
</style>