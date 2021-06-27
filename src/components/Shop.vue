<template>
<div>
    <div class="text-center">
        <h1>Products</h1>
        <div class="row" v-for="(product, i) in products" :key="i" :product="product">
            <div class="col">{{product.name}}</div>
            <div class="col">Price: ${{product.price}}</div>
            <button class="col-2 btn btn-success" @click="addToCart(product)">Add to cart</button>
        </div>
    </div>
        <div class="text-center">
        <h1>Cart ({{cart.length}})</h1>
        <div class="row" v-for="product in cart" :key="product.id" :item="product">
        <div class="col">{{product.name}}</div>
        <div class="col">Count: {{product.count}}</div>
        <div class="col">Price: ${{product.total}}</div>
        <button class="col-1 btn btn-success" @click="addToCart(product)">+</button>
        <button class="col-1 btn btn-danger" @click="decreaseCartItem(product)">-</button>
        </div>
        <div class="col">Total: ${{total}}</div>
    </div>
</div> 
</template>

<script>

export default {
  computed: {
    singleCost () {
      let cost = 0;
      this.cart.forEach((i) => {
        cost = i.price * i.count;
      });
      return cost;
    },
    total () {
      let totalCost = 0
      for (let i in this.cart) {
        totalCost += this.cart[i].price * this.cart[i].count
      }
      return totalCost;
    },
  },
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
          product.total = product.price
        } else {
          product.count++
          product.total = product.price * product.count
        }
    },
    decreaseCartItem(product) {
      if (product.count == 1) {
        this.cart.splice(this.cart.indexOf(product), 1);
      } else {
      product.count--
      product.total = product.price * product.count
      }
    }
  }
}
</script>

<style>

</style>