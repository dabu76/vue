<template>
  <div class="menu">
    <a v-for="作名 in メニュー" :key="作名">{{ 作名 }}</a>
  </div>
  1kショップ
  <div v-for="(room, i) in products" :key="room">
    <h4 class="red" :style="スタイル">{{ room }} 1k</h4>
    <p>{{ price[i] }}万円</p>
    <button @click="increase(i)">report</button>
    <span>count :{{ counts[i] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      メニュー: ["Home", "Shop", "About"],
      price: [60, 70, 80],
      スタイル: "color:blue",
      products: ["伏見k", "浄心1k", "浅間町1k"],
      counts: [0, 0, 0],
    };
  },
  methods: {
    increase(i) {
      if (i === 0) {
        this.counts[0] += 1;
      } else if (i === 1) {
        this.counts[1] += 1;
      } else if (i === 2) {
        this.counts[2] += 1;
      }
    },
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
  color: white;
  padding: 10px;
}
</style>
