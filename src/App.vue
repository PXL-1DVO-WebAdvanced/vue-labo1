<template>
  <div>
    <login v-if="!username" @userLogin="onUserLogin"/>
    <div id="main" v-else>
      <nav-bar :username="username" @userLogout="onUserLogout"/>

      <div class="main-content container-fluid">
        <div class="row">
          <div class="col-4">
            <form>
              <fieldset>
                <caption>Filter</caption>
                <input type="text" class="form-control" v-model="searchText" placeholder="Zoek op titel">
              </fieldset>
            </form>
            <comparison-list 
              :products="comparedProducts"
              @removeFromComparison="removeProductFromComparison" />
          </div>
          <div class="col-8 product-list">
            <product-card
              v-for="product in filteredProducts"
              :key="product.id"
              :product="product"
              @changeCompare="changeProductCompare" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Login from './components/LoginComponent.vue';
import NavBar from './components/NavBarComponent.vue';
import ProductCard from './components/ProductCardComponent.vue'; 
import ComparisonList from './components/ComparisonListComponent.vue';
import { uniqueNamesGenerator, animals } from 'unique-names-generator';


export default {
  components: { 
    Login,
    NavBar,
    ProductCard,
    ComparisonList
  },
  computed: {
    comparedProducts() {
      return this.products.filter(p => p.compare == true)
    },
    filteredProducts() {
      if(this.searchText)
          return this.products.filter(product =>
          product.title.toLowerCase().includes(this.searchText.toLowerCase()));
      else
          return this.products;
    }
  },
  data() {
    return {
      username: null,
      products: this.getSomeProducts(),
      searchText: ''
    }
  },
  methods: {
    onUserLogin(username) {
      this.username = username;
    },
    onUserLogout() {
      this.username = null;
    },
    changeProductCompare(object) {
      console.log(`changeProductCompare(${object.compare})`)
      let product = this.products.find(p => p.id === object.id)

      if(product) {
        product.compare = object.compare;
      }
    },
    removeProductFromComparison(productId) {
      console.log(`removeProductFromComparison(${productId})`)
      let product = this.products.find(p => p.id === productId)
      console.log(product)
      if(product) {
        product.compare = false;
      }
    },
    getSomeProducts() {
      return [
          {
            id: 1,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 2,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 3,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 4,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 5,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 6,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 7,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 8,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 9,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 10,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 11,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          },
          {
            id: 12,
            title: this.randomName(),
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            price: this.randomPrice(),
            compare: false
          }
        ]
    },
    randomName() {
      const config = {
        dictionaries: [animals],
        separator: ' ',
        style: 'capital'
      }
      return uniqueNamesGenerator(config); 
    },
    randomPrice() {
      return Math.round((Math.random() + Math.random()) * 10000) / 100;
    }
  }
}
</script>
<style lang="scss">
  .username {
    text-align: right !important;
  }
  .product-list {
    padding: 1rem;
    display: flex;
    flex-wrap: wrap;
  }
  fieldset {
    border: 1px solid lightgray;
    border-radius: 5px;
    margin: 1rem;
    padding: 1rem;
    caption {
      font-weight: bold;
      width: 50%;
    }
  }
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