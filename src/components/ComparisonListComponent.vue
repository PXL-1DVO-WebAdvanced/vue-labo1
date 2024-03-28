<template lang="html">
    <fieldset v-show="products.length > 0">  
        <caption>Vergelijk</caption>
        <ul class="product-comparison list-unstyled">
            <li v-for="product in products" :key="product.id">
                <i class="bi bi-trash" @click="remove(product.id)"></i>
                <span>{{ product.title }}</span>
            </li>
        </ul>
        <button class="btn btn-primary">Vergelijk deze producten!</button>
    </fieldset>
</template>
<script>
export default {
    props: [
        'products'
    ],
    emits: [
        'removeFromComparison'
    ],
    methods: {
        remove(id) {
            console.log(id)
            this.$emit('removeFromComparison', id)
        }
    }
}
</script>
<style lang="scss">
    
</style>