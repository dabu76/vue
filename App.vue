<template>
  <div class="menu">
    <a v-for="作名 in メニュー" :key="作名">{{ 作名 }}</a>
  </div>
  <div>
    1kショップ
    <h4 class="red" :style="スタイル">{{ products[0] }} 1k</h4>
    <p>{{ price1 }}万円</p>
  </div>
  <div>
    <h4 class="red" :style="スタイル">{{ products[1] }}1k</h4>
    <p>{{ price2 }}万円</p>
  </div>
  <div>
    <h4 class="red" :style="スタイル">{{ products[2] }}1k</h4>
    <p>{{ price3 }}万円</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      メニュー: ["Home", "Shop", "About"],
      price1: 60,
      price2: 70,
      price3: 80,
      スタイル: "color:blue",
      products: ["伏見k", "浄心1k", "浅間町1k"],
    };
  },
  components: {},
};
</script>

<style>
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color {
    color: white;
    padding: 10px;
  }
}
</style>
