<template>
  <div class="card card-1">
      <img :src="data.img" />
      <h4> {{ data.title }} </h4>
      <button> 
          Go Shop
      </button>
  </div>
</template>

<script>
import { toRefs } from 'vue'
export default {
    props:['data'],
    setup(props){
        const { data }  =  toRefs(props);

        return { 
            data
        }
    }

}
</script>

<style scoped>
    .card {
        background: #fff;
        border-radius: 2px;
        display: inline-block;
        margin: 1rem;
        position: relative;
        width: 300px;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 10px;
    }

    .card-1 {
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
        transition: all 0.3s cubic-bezier(.25,.8,.25,1);
    }

    .card-1:hover {
        box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
    }

    img {
        height: 200px;
        width: 200px;
        object-fit: contain;
        border-radius: 50%;

    }
    button { 
        border:none;
        background: #42b983;
        border-radius: 10px;
        padding: 8px;
        color: #fff;
        font-weight: bold;
    }

</style>