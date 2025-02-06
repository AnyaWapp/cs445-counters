<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
//import ref
</script>

<template>
  <h4>Item Counters</h4>
      <div v-for="product in products" 
          class="product"
          >
              <span class="name">{{product.name}}</span>
              <div class="quantity-area">
                  <template v-if="product.active">
                      <button :disabled="product.quantity<=0" @click.stop="product.quantity--">-</button> 
                      <span class="quantity">{{product.quantity}}</span> 
                      <button @click.stop="product.quantity++">+</button>
                  </template>
              </div>
      </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
      {
        "name": "Eggs",
        "quantity": 1,
        active: true
    },
    {
        "name": "Tortillas",
        "quantity": 1,
        active: true
    },
    {
        "name": "Chocolate",
        "quantity": 1,
        active: true
    }
      ]
    };
  },
  methods: {
    toggleActive: function(item){
            item.active = !item.active;
        },
  }
}
</script>

<style scoped>
h4 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

.product {
  margin-bottom: 3rem;
}


.quantity {
  margin: 0 10px;
}

button:disabled {
  background-color: #ccc; 
}

button {
  padding: 0.5rem;
  background-color: #00ff84;
  color: white;
}

</style>
