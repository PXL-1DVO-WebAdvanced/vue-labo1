<template lang="html">
    <fieldset id="comparison">  
        <caption>Vergelijk</caption>
        <ul class="product-comparison list-unstyled">
            <li>
                <i class="bi bi-trash"></i>
                <span>Insert product-title here</span>
            </li>
        </ul>
        <button class="btn btn-primary">Vergelijk deze producten!</button>
    </fieldset>
</template>
<script>
export default {
    emits: [
        'removeFromComparison'
    ],
    methods: {
        remove(id) {

        }
    }
}
</script>
<style lang="scss">
    .product-comparison {
        padding: 1rem;
        li {
            margin-bottom: 2rem;
            display: flex;
            align-items: center;
            border-bottom: 1px solid lightgray;
            i {
                font-size: 1.5rem;
                margin-right: 2rem;
            }
        }
    }
</style>