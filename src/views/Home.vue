<template>
  <div class="home">
    <Banner />
    <TopSellers />
  </div>
</template>

<script>
import Banner from '@/components/Banner.vue';
import TopSellers from '@/components/TopSellers.vue';


export default {
  name: 'Home',
  components: {
    Banner,
    TopSellers
   }

}
</script>

<style scoped>
     
</style>