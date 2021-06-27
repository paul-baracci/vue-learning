<template>
<div>
    <div class="text-center">
        <h1>Products</h1>
        <div class="row" v-for="(product, i) in products" :key="i" :product="product">
            <div class="col">{{product.name}}</div>
            <div class="col">Price: ${{product.price}}</div>
            <button class="col btn btn-success" @click="addToCart(product)">Add to cart</button>
        </div>
    </div>
        <div class="text-center">
        <h1>Cart items {{cart.length}}</h1>
        <div class="row" v-for="product in cart" :key="product.id" :item="product">
        <div class="col">{{product.name}}</div>
        <div class="col">Price: ${{product.price}}</div>
        <div class="col">Count: {{product.count}}</div>
        <button class="col btn btn-danger" @click="removeFromCart(product)">x</button>
        </div>
    </div>
</div> 
</template>

<script>

export default {
  data() {
    return {
      cart: [],
      products: [
        {
          id: 1,
          name: "Prod1",
          price: 20,
          count: 1
        },
        {
          id: 2,
          name: "Prod2",
          price: 100,
          count: 1
        }
      ]
    }
  },
  methods: {
    addToCart(product) {
      let found = this.cart.some(item => item.id === product.id)
        if(found == 0) {
          this.cart.push(product);
        } else {
          product.count++
        }
    },
    removeFromCart(product) {
      this.cart.splice(this.cart.indexOf(product), 1);
    },
  }
}
</script>

<style>

</style>