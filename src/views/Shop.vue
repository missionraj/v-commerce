<template>
   <div class="ShopContainer">  
      <div> 
         <h4> Categories </h4> 
         <div class="Categories">
            <div class="category--wrapper" v-for="category in categories" :key="category.id">
               <div class="MainCategory"> {{ category.mainCat.name }}  
                  <i v-if="!category.show" class="pi pi-arrow-circle-right"  @click="show(category.id)"> </i> 
                  <i v-if="category.show" class="pi pi-arrow-circle-down" @click="hide(category.id)"></i>
                  </div>
               <div class="SubCategory" :class="{'SubCategoryShow':category.show}"> 
                  <div v-for="subcat in category.mainCat.subCat" :key="subcat.id">  {{ subcat.name}} </div>
               </div>
            </div>
         </div>
      </div>   
      <div> 
          

      </div>   
   </div>  
</template>

<script>
import { ref } from 'vue'
export default {
    setup(){
       
      const showCategory = ref(false)

      const categories = ref([
         {
            id:1,
            mainCat:{
                  name:'Men',
                  subCat:[
                     {
                        id:1,
                        name:'shirt'
                     },
                     {
                        id:2,
                        name:'jeans'
                     },
                     {
                        id:3,
                        name:'shorts'
                     },
                     {
                        id:4,
                        name:'bermuda'
                     }
                  ]
            }
         },
         {
            id:2,
            mainCat:{
                  name:'Women',
                  subCat:[
                     {
                        id:1,
                        name:'Top'
                     },
                     {
                        id:2,
                        name:'Bottom'
                     },
                     {
                        id:3,
                        name:'Accessories'
                     }
                  ]
            }
         },
         {
            id:3,
            mainCat:{
                  name:'Kids',
                  subCat:[
                     {
                        id:1,
                        name:'Clothes'
                     },
                     {
                        id:2,
                        name:'footwears'
                     }
                  ]
            }
         }
      ])
      const show = (catid) =>  {
         const selectedCat = categories.value.filter(cat=> cat.id == catid)[0]
         selectedCat.show = true
      }
      const hide = (catid) =>  {
         const selectedCat = categories.value.filter(cat=> cat.id == catid)[0]
         selectedCat.show = false
      }
      return {  showCategory , show, hide, categories }
    }
}
</script>

<style scoped>
   .ShopContainer { 
      display: flex;
      justify-content: space-between;
      margin-left: auto;
      margin-right: auto;
      padding: 1em 2.5em;
      max-width: 1140px;
   }
   .Categories { 
      font-size: 18px;
   }

   .category--wrapper { 
      width: 300px;
      overflow: hidden;
   }
   .MainCategory {
      display: flex;
      justify-content: space-between;
      align-items: center;
   }

   .SubCategory {
      max-height: 0;
      padding-left: 8px;
      transition: max-height 0.5s ease-in;
      overflow: hidden;
   }

   .SubCategoryShow { 
      max-height: 10em;
   }
   
</style>