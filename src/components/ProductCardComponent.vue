<template>
    <div class="card product-card">
      <img src="../assets/notfound.jpg"/>
      <div class="card-body">
        <h5 class="card-title">{{ product.title }}</h5>
        <p class="card-text">{{ product.description }}</p>
      </div>
      <div class="card-body ">
        <p class="price">€ {{ product.price }}</p>
        <div class="d-flex align-items-center">
          <input :id="product.id" type="checkbox" v-model="product.compare" @change.stop.prevent="changeComparison" />
          <label :for="product.id">Vergelijk</label>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: [
      'product'
    ],
    emits: [
      'changeCompare'
    ],
    methods: {
        changeComparison(event) {
            console.log(event.target.checked)
            this.$emit('changeCompare', {id: this.product.id, compare: event.target.checked})
        }
    }
  };
</script>
  
<style scoped lang="scss">
  .product-card {
    max-width: 30%;
    margin: 0 1.5% 2rem 1.5%;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  
    h3 {
      margin-bottom: 10px;
    }

    img {
      width: 100%;
    }

    .price {
      font-weight: bold;
    }

    input[type="checkbox"] {
      width: 1.5rem;
      height: 1.5rem;
      margin-right: 1rem;
    }
  }
  
</style>
  