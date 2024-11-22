<script>
export default {
    name: 'Product',
    props: {
        productData: {
            type: Object,
            required: true,
        },
    },
};
</script>

<template>
    <div class="product">
        <div class="product__image">
            image
        </div>
        <div class="product__details">
            <h1>{{ productData.title }}</h1>
            <div>${{ productData.price }}.00</div>
            <p>{{ productData.description }}</p>
            <div class="product__sizes">
                <div>
                    Size<span>*</span>:
                    <span>selected size here</span>
                </div>
                <button v-for="sizeOption in productData.sizeOptions">
                    {{ sizeOption.label }}
                </button>
            </div>
            <button>Add to cart</button>
        </div>
    </div>
</template>
