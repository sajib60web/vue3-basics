<template>
  <div class="product-card">
    <div class="product-card__title">{{ product.name }}</div>
    <div class="product-card__body">
      <img :src="product.thumbnail" alt="Image" />
      <p>{{ product.price }}</p>
    </div>
    <div class="product-card__footer">
      <button @click="handleBuyNowClick">Buy Now</button>
      <button @click="handleAddToCartClick">Add to Cart</button>
    </div>
  </div>
</template>
<script>
export default {
  props: { product: { type: Object, default: () => ({}) } },
  methods: {
    handleBuyNowClick() {
      this.$emit("buy-now-clicked", this.product);
    },
    handleAddToCartClick() {
      this.$emit("add-to-cart-clicked", this.product);
    },
  },
};
</script>
<style>
.product-card {
  width: 200px;
  width: 300px;
  border: 1px solid #006f88;
  min-height: 200px;
  min-height: 100px;
  margin: 22px auto;
}
.product-card__title {
  background: #167db1;
  padding: 5px 11px;
  color: #fff;
}
.product-card__body {
  padding: 11px;
  text-align: center;
}
.product-card__body img {
  text-align: center;
  height: 111px;
}
.product-card__footer {
  background: #e3e3e3;
  padding: 5px 11px;
  text-align: center;
}
</style>
