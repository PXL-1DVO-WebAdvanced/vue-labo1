<template>
  <div>
    <login />

    <div id="main">
      <!-- TODO: insert NavBarComponent here! -->
      <div class="main-content container-fluid">
        <div class="row">
          <div class="col-4">
            <!-- TODO: insert filter-form here! -->
            <!-- TODO: insert ComparisonListComponent here!  -->
          </div>
          <div class="col-8 product-list">
            <!-- TODO: insert ProductCardComponent here! -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Login from './components/LoginComponent.vue';

// Onderstaande module wordt gebruik om random productnamen te genereren:
import { uniqueNamesGenerator, animals } from 'unique-names-generator';


export default {
  components: { 
    Login
  },
  data() {
    return {
      username: null,
      products: this.getSomeProducts()
    }
  },
  methods: {
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
</style>