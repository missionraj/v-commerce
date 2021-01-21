<template>
    <h2 class="text-center"> Top Sellers ... </h2>
    <div class="seller__wrapper"> 
         <div v-for="TopSeller in TopSellers" :key="TopSeller.id">
            <TopSellingCard :data="TopSeller"/>
         </div>
    </div>
</template>

<script>
import TopSellingCard from "@/components/TopSellingCard.vue";
import { ref } from 'vue';

export default {
    components: {
        TopSellingCard
    },
    setup(){
        const TopSellers = ref([
            {
                id:1,
                img:require('@/assets/images/category_img_01.jpg'),
                title:'Watches',
                details:'test'
            },
            {
                id:2,
                img:require('@/assets/images/category_img_02.jpg'),
                title:'Shoes',
                details:'test'
            },
            {
                id:3,
                img:require('@/assets/images/category_img_03.jpg'),
                title:'Accesories',
                details:'test'
            }
        ])
        return {
            TopSellers
        }
    }
}
</script>

<style scoped>
    .seller__wrapper { 
        display: flex;
        align-items: center;
        justify-content: space-around;
        background: #e2e1e0;
    }
</style>