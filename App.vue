<template>
  <div class="menu">
    <a v-for="作名 in メニュー" :key="作名">{{ 作名 }}</a>
  </div>
  1kショップ
  <div v-for="room in products" :key="room">
    <h4 class="red" :style="スタイル">{{ room }} 1k</h4>
    <p>{{ price1 }}万円</p>
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
