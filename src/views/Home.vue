<template>
  <div class="home">
    <Banner />
    <TopSellers />
    <FeaturedProducts />
  </div>
</template>

<script>
import Banner from '@/components/Banner.vue';
import TopSellers from '@/components/TopSellers.vue';
import FeaturedProducts from '@/components/FeaturedProducts.vue';


export default {
  name: 'Home',
  components: {
    Banner,
    TopSellers,
    FeaturedProducts
   }

}
</script>

<style scoped>
     
</style>