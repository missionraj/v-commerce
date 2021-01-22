<template>
  <div class="footer_Wrapper">
      <div> 
        <router-link class="Logo" :to="{name:'Home'}"> V-commerce </router-link>
      </div>
      <div class="links_wrapper"> 
        <h2 class="heading"> More </h2>
        <div>   
            <router-link :to="{name:'Home'}"> Home </router-link>    
        </div>
        <div>   
            <router-link :to="{name:'Shop'}"> Shop </router-link>    
        </div>
        <div>   
            <router-link :to="{name:'About'}"> About </router-link>    
        </div>   
      </div>
      <div> 
          <h2 class="heading"> Social Connect </h2>
          <div> 
              <i class="pi pi-twitter"></i>
          </div>
          <div> 
              <i class="pi pi-github"></i>
          </div> 
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .footer_Wrapper { 
        background: #212934;
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        flex-wrap: wrap;
    }

    .heading { 
        font-weight: 300;
        border-bottom: 1px solid #dee2e6;
    }

    .Logo {
        color: #42b983;
        font-size: 3rem;
        font-weight: bold;
        text-decoration: none;
        padding: 20px;
    }

    .links_wrapper a {
        color: #fff;
        text-decoration: none;
        font-size: 18px;
        transition: transform 0.5s; /* Animation */
    }
    .links_wrapper a:hover { 
        color: #42b983;
        transform: scale(1.2);
    }
</style>