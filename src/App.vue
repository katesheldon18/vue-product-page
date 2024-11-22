<script>
import Header from './components/Header/Header.vue';
import Product from './components/Product/Product.vue';

export default {
    name: 'App',
    components: {
        Header,
        Product,
    },
};
</script>

<template>
    <div id="app">
        <h1>Hello world here is the App</h1>
        <Header />
        <Product />
    </div>
</template>
