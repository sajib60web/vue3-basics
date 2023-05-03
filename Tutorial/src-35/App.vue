<template>
  <div>
    <header>
      <h2 class="">{{ title }}</h2>
    </header>
    <the-card cardTitle="About Me">
      <template v-slot:default>
        <p>Hi, I am Sajib Kumar Barai</p>
      </template>
      <template v-slot:footer>
        <a href="https://tricksoftbd.com">Learn More</a>
      </template>
    </the-card>
    <the-card cardTitle="Apple iPhone 12 Pro">
      <template v-slot:default>
        <img
          src="https://fdn2.gsmarena.com/vv/bigpic/apple-iphone-12-pro--.jpg"
          alt="Image"
        />
        <p>
          Versions: A2407 (International); A2341 (USA); A2406 (Canada, Japan);
          A2408 (China, Hong Kong)
        </p>
      </template>
      <template #footer>
        <button>Buy Now</button>
        <button>Add to Cart</button>
      </template>
    </the-card>
  </div>
</template>
<script>
import TheCard from "./TheCard.vue";
export default {
  components: {
    TheCard,
  },
  data() {
    return {
      title: "Vue 3 Bangla Tutorial",
    };
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
