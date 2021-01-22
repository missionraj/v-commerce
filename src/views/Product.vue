<template>
  <div class="product_detail"> 
      <div class="productImage__Wrapper">
          <img class="productImage__Wrapper--main" src='@/assets/images/product_single_01.jpg' alt="">
      </div>
  </div>
</template>

<script>
import { toRefs } from 'vue'
export default {
    props:['id'],
    setup(props){
        const { id } =  toRefs(props)
        return { 
            id
        }
    }
}
</script>

<style scoped>

    .product_detail { 
        display: flex;
        background: #e9eef5;
        margin-left: auto;
        margin-right: auto;
        padding: 1em 2.5em;
    }
    .productImage__Wrapper--main { 
        width: 300px;
        height: auto;
    }
</style>