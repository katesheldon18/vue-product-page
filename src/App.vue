<script>
import Header from './components/Header/Header.vue';
import Product from './components/Product/Product.vue';

export default {
    name: 'App',
    components: {
        Header,
        Product,
    },
    data() {
        return {
            productData: {},
        };
    },
    async mounted() {
        this.productData = await fetchProductData();
    },
};

async function fetchProductData() {
    try {
        const res = await fetch('https://3sb655pz3a.execute-api.ap-southeast-2.amazonaws.com/live/product');
        const productData = await res.json();
        console.log(productData);
        return productData;
    } catch (error) {
        console.log('error fetching product data', error);
        return null;
    }
}

</script>

<template>
    <div id="app">
        <Header />
        <Product :product-data="productData" />
    </div>
</template>
