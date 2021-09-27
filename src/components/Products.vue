<template>
    <div class="jumbo-container">
        <div class="jumbotron">
            <img :src="require(`@/assets/${jumbo[0].img}`)" :alt="jumbo[0].altText">
        </div>
        <div class="container">
            <div class="product">
                <ProductCard 
                v-for="(product, index) in products"
                :key="index"
                :prod="product"
                />
            </div>
            <button>LOAD MORE</button>

        </div>
        
    </div>
</template>

<script>
import ProdItems from '@/assets/data/DCComics.js'
import ProductCard from '@/components/ProductCard.vue'
import Jumbotron from '@/assets/data/Jumbotron.js'
export default {
    name: 'Products',
    components: {
        ProductCard,
    },
    data(){
        return{
            products: ProdItems,
            jumbo: Jumbotron,
        }
    },
}
</script>

<style scoped lang="scss">
@import '@/style/general.scss';

.jumbo-container{
    background-color: $black;
    
    .jumbotron{
        height: 450px;

        img{
            height: 100%;
            width: 100%;
            object-position: top;
            object-fit: cover
        };
    }

    .current-series{
        display: inline-block;
        width: max-content;
        position: absolute;
        top: 0;
        left: 0;
        transform: translateY(-50%);
        height: 50px;

        background-color: $blue;
        padding: 0px 15px;
        color: $txt-light;
        font-size: $fs-xl;
    }

    .product{
        @include center(horizontal);
        flex-wrap: wrap;
        padding: 50px 0px;
    }
    
    .container{
        @include centerCol(horizontal);
        button{
            width: max-content;
            margin-bottom: 30px;
        }
        @include button(colored);

    }

}


</style>