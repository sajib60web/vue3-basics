<template>
  <div class="product-card">
    <div class="product-card__title">
      <div>{{ product.name }}</div>
      <img
        src="./img/star.png"
        v-if="product.addedToFavorite"
        style="height: 30px"
        alt="Star"
        @click="toggleFavorite"
      />
      <img
        src="./img/un-star.png"
        v-else
        style="height: 30px"
        alt="Star"
        @click="toggleFavorite"
      />
    </div>
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
  emits: {
    "buy-now-clicked": function (data) {
      if (!data) {
        console.error("data missing for buy now click event");
        return false;
      }
      return true;
    },
    "add-to-cart-clicked": function (data) {
      if (!data) {
        console.error("data missing for add to cart click event");
        return false;
      }
      return true;
    },
  },
  methods: {
    handleBuyNowClick() {
      this.$emit("buy-now-clicked", this.product);
    },
    handleAddToCartClick() {
      this.$emit("add-to-cart-clicked", this.product);
    },
    toggleFavorite() {
      this.$emit("toggle-favorite", this.product);
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
  display: flex;
  justify-content: space-between;
  align-items: center;
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
