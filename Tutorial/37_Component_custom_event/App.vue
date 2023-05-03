<template>
  <div>
    <header>
      <h2 class="">{{ title }}</h2>
    </header>
    <product-card
      v-for="product in products"
      :key="product.name"
      :product="product"
      @buy-now-clicked="buyNow"
      @add-to-cart-clicked="addToCard"
    ></product-card>
  </div>
</template>
<script>
import ProductCard from "./ProductCard.vue";
export default {
  components: {
    ProductCard,
  },
  data() {
    return {
      title: "Vue 3 Bangla Tutorial",
      products: [
        {
          name: "Apple iPhone 11 Pro",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro--.jpg",
          price: "৳61999",
        },
        {
          name: "Apple iPhone 12 Pro",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro--.jpg",
          price: "৳61999",
        },
        {
          name: "Apple iPhone 13 Pro",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro--.jpg",
          price: "৳61999",
        },
        {
          name: "Apple iPhone 14 Pro",
          thumbnail:
            "https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro--.jpg",
          price: "৳61999",
        },
      ],
    };
  },
  methods: {
    buyNow(product) {
      console.log(product);
      console.log("Buying...");
    },
    addToCard() {
      console.log("Adding...");
    },
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
ul {
  margin-left: 22px;
}
body {
  font-family: sans-serif;
  line-height: 1.8;
}
header {
  background-color: #1f2c46;
  color: #41b883;
  font-size: 22px;
  padding: 22px;
}

header h2 {
  text-align: center;
}
button {
  margin: 5px;
  padding: 5px 11px;
  cursor: pointer;
}
</style>
