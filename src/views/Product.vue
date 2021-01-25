<template>
    <section class="bg-light-grey">
        <div class="product_detail" > 
            <div class="productImage__Wrapper" >
                <img class="productImage__Wrapper--main" src='@/assets/images/product_single_01.jpg' alt="" />
            </div>
            <div class="Product__description">
                <h2> Active Wear </h2>
                <p> $25 </p>
                <p> <strong> Brand </strong> : <span> Levis </span> </p>
                <h4> Description : </h4>
                <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod temp incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse. Donec condimentum elementum convallis. Nunc sed orci a diam ultrices aliquet interdum quis nulla. </p>
                <h4> Specification : </h4>
                <p> 
                    Lorem ipsum dolor sit
                    Amet, consectetur
                    Adipiscing elit,set
                    Duis aute irure
                    Ut enim ad minim
                    Dolore magna aliqua
                    Excepteur sint
                </p>
                <div class="Product__description--button"> 
                    <button>  Buy Now  </button>
                    <button>  Add To Cart  </button>
                </div>
            </div>
        </div>  
    </section>
    <section >
        <div class="RelatedProducts__container">
            <h2> Related Products </h2>
            <Carousel :value="relatedProducts" :numVisible="3" :numScroll="1" >
                <template #item="slotProps" > 
                    <FeaturedProductCard :details="slotProps.data" />
                </template>
            </Carousel>
        </div>
    </section>
</template>

<script>
import { toRefs, ref } from 'vue'

import Carousel from 'primevue/carousel'

import FeaturedProductCard from "@/components/FeaturedProductCard";

export default {
    props:['id'],
    components : { Carousel, FeaturedProductCard },
    setup(props){
        const { id } =  toRefs(props)
        const relatedProducts = ref([
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
            },
            {
                id:4,
                title: 'Watch',
                description : 'this is description ...',
                price: 200,
                img:require('@/assets/images/featured_watch.jpg')
            },
            {
                id:5,
                title: 'Watch',
                description : 'this is description ...',
                price: 200,
                img:require('@/assets/images/featured_watch.jpg')
            },
            {
                id:6,
                title: 'Watch',
                description : 'this is description ...',
                price: 200,
                img:require('@/assets/images/featured_watch.jpg')
            },
            {
                id:7,
                title: 'Watch',
                description : 'this is description ...',
                price: 200,
                img:require('@/assets/images/featured_watch.jpg')
            }
        ])
        return { 
            id,
            relatedProducts
        }
    }
}
</script>

<style scoped>

    .product_detail { 
        display: flex;
        justify-content: space-between;
        margin-left: auto;
        margin-right: auto;
        padding: 1em 2.5em;
        max-width: 1140px;
    }
    .productImage__Wrapper { 
        width: 40%;
    }
    .productImage__Wrapper--main { 
        width: 300px;
        height: auto;
        width: 100%;
    }

    .Product__description{
        background: #fff;
        border: 1px solid rgba(0,0,0,.125);            
        padding: 0 10px;
        width: 58%;
    }

    .Product__description--button { 
        display: flex;
        align-items: center;
        justify-content: space-evenly;
    }

    .Product__description--button > button {
        background: #59ab6e;
        border:none;
        width: 250px;
        padding: 10px;
        border-radius: 5px;
        color: #fff;
        font-weight: 700;
    }

    .RelatedProducts__container { 
        margin-left: auto;
        margin-right: auto;
        padding: 1em 2.5em;
        max-width: 1140px;
    }

    @media only screen and (max-width: 768px) {
        .product_detail { 
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            margin-left: auto;
            margin-right: auto;
            padding: 1em 2.5em;
            max-width: 1140px;
        }

        .productImage__Wrapper { 
            width: 100%;
            margin-bottom: 1em;
        }
        
        .Product__description{
            background: #fff;
            border: 1px solid rgba(0,0,0,.125);            
            padding: 0 10px;
            width: 100%;
        }

        .Product__description--button { 
            display: flex;
            align-items: center;
            flex-direction: column;
        }

        .Product__description--button > button {
            background: #59ab6e;
            border:none;
            width: 250px;
            padding: 10px;
            border-radius: 5px;
            color: #fff;
            font-weight: 700;
            margin-bottom: 1em;
        }
    }
</style>