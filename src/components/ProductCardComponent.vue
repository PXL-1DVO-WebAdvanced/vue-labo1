<template>
    <div class="card product-card">
      <img src="../assets/notfound.jpg"/>
      <div class="card-body">
        <h5 class="card-title">...</h5>
        <p class="card-text">...</p>
      </div>
      <div class="card-body ">
        <p class="price">€ ...</p>
        <div class="d-flex align-items-center">
          <input type="checkbox" />
          <label>Vergelijk</label>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    
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
  