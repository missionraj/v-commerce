<template>

    <div class="card" @click="navigateToProductDetail"> 
        <img :src="details.img" >
        <div> {{ details.price }} </div>
        <div class="title"> {{ details.title }} </div> 
        <p> {{ details.description }} </p>
    </div>

</template>

<script>
import { toRefs } from 'vue'

import { useRouter } from 'vue-router'

export default {
    props:['details'],
    setup(props) { 
        const { details } =  toRefs(props)
    
        const router = useRouter()

        const navigateToProductDetail = () => {
            router.push({ name: 'Product', params: { id : details.value.id }}) 
        }

        return {
            details,
            navigateToProductDetail
        }
    }
}
</script>

<style scoped>

 .card { 
     width:300px;
     border: 1px solid rgba(0,0,0,.125);
     border-radius: 8px;
 }

 img { 
     width: 100%;
     height: 300px;
     object-fit: cover;
 }

 .title { 
     font-size: 30px;
     font-weight: 600;
 }


</style>