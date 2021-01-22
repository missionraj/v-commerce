<template>
    <div id="nav">
        <div class="nav__Logo">
            <router-link :to="{name:'Home'}"> V-commerce </router-link>    
        </div>
        <div class="nav__items" > 
            <router-link :to="{name:'Home'}" > Home </router-link> 
            <router-link :to="{name:'About'}" > About </router-link>
            <router-link :to="{name:'Shop'}" > Shop </router-link>
        </div>
        <div class="nav__iconsWrapper">
            <i class="pi pi-search"></i>         
            <i class="pi pi-shopping-cart"></i>      
            <i class="pi pi-user"></i>            
        </div>
    </div>
    <div class="mobile-nav">
        <div class="mobile__nav--items">
            <div class="nav__Logo">
                <router-link :to="{name:'Home'}"> V-commerce </router-link>    
            </div>
            <div>
                <i class="pi pi-bars" @click="showAndHide"></i>
            </div>
        </div>
        <div class="hidden-contents" :class="{'show-contents': showMobileMenu }">
            <div>
                <router-link :to="{name:'Home'}" > Home </router-link> 
            </div>
            <div>
                <router-link :to="{name:'About'}" > About </router-link>
            </div>
            <div>
                <router-link :to="{name:'Shop'}" > Shop </router-link>
            </div>
            <div class="nav__iconsWrapper">
                <i class="pi pi-search"></i>         
                <i class="pi pi-shopping-cart"></i>      
                <i class="pi pi-user"></i>            
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue'

export default {
    setup(){
        const showMobileMenu = ref(false)

        const showAndHide = () =>  {
            showMobileMenu.value = !showMobileMenu.value
        }
        return {  showMobileMenu , showAndHide }
    }
}
</script>

<style scoped>
    #nav {
        padding: 30px;
        display: flex;
        justify-content: center;
        align-items:center;
        margin-right: auto;
        margin-left: auto;
    }
    .nav__Logo a {
        color: #42b983;
        font-size: 3rem;
        font-weight: bold;
        text-decoration: none;
        padding: 20px;
    }

    .nav__items { 
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-left: auto;
        margin-right: auto;
    }
    .nav__items a { 
        color: black;
        text-decoration: none;
        padding: 20px;
        font-size: 18px;
        transition: transform 0.5s; /* Animation */
    }
    .nav__items a:hover { 
        color: #42b983;
        transform: scale(1.2);
    }
    .nav__iconsWrapper { 
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .nav__iconsWrapper i { 
        padding: 10px;
    }

    .mobile-nav {
        display: none; 
        padding: 1em;
    }
    @media only screen and (max-width: 768px) {
            #nav{
                display: none;
            }
            .mobile-nav {
                display: block; 
                padding: 1em;
            }
            .mobile__nav--items { 
                display: flex;
                align-items: center;
                justify-content: space-between;
            }
            .hidden-contents { 
                display: none;
                overflow: hidden;
                transition: display 1s;
            }
            .show-contents { 
                display: block;
            }
            .hidden-contents a { 
                color: black;
                text-decoration: none;
                padding: 20px;
                font-size: 18px;
                transition: transform 0.5s; /* Animation */
            }
            .hidden-contents a:hover { 
                color: #42b983;
                transform: scale(1.2);
            }
            .nav__Logo a {
                color: #42b983;
                font-size: 2rem;
                font-weight: bold;
                text-decoration: none;
            }
    }


</style>