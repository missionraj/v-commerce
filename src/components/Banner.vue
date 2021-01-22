<template>
  <Carousel :value="banner" >
            <template #item="slotProps" > 
                <div class="container">
                    <div >
                        <h1> {{ slotProps.data.title }} </h1>
                        <h3> {{ slotProps.data.detail }} </h3>
                        <p> {{ slotProps.data.description }} </p>
                    </div>
                    <img :src="slotProps.data.img" />
                </div>
            </template>
  </Carousel>
</template>

<script>
import Carousel from 'primevue/carousel';
import { ref } from 'vue';
export default {
props:[],
components : { 
    Carousel
},
setup (props) {
    const banner =  ref([
        {
            title: ' product 1',
            detail: 'Where does it come from?',
            description: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
            img: require('@/assets/images/banner_1.jpg')
        },
        {
            title: ' product 2',
            detail: 'Where does it come from?',
            description: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
            img: require('@/assets/images/banner_2.jpg')
        },
        {
            title: ' product 3',
            detail: 'Where does it come from?',
            description: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
            img: require('@/assets/images/banner_3.jpg')
        },
        {
            title: ' product 4',
            detail: 'Where does it come from?',
            description: 'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
            img: require('@/assets/images/banner_4.jpg')
        }
    ])   
    return { 
        banner
    }
}
}
</script>

<style scoped>
    .container { 
        max-width: 1140px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background: #efefef;
        margin-left: auto;
        margin-right: auto;
        padding: 1em;
        flex-direction: column-reverse;
    }
    img { 
        height: 400px;
        max-width: 400px;
        object-fit: contain;
    }

    @media only screen and (max-width: 768px) {
        .container { 
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            background: #efefef;
            padding: 1em;
        }
        img { 
            height: 300px;
            width: 100%;
            object-fit: contain;
        }
    }
</style>