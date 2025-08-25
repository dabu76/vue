<template>
  <div class="black-bg" v-if="modal_open === true">
    <div class="white-bg">
      <h4>詳細ページ</h4>
      <p>詳細ページ内容</p>
      <button @click="modal_open = false">閉じる</button>
    </div>
  </div>
  <div class="container">
    <div class="menu">
      <a v-for="作名 in メニュー" :key="作名">{{ 作名 }}</a>
    </div>
    1kショップ

    <div v-for="(room, i) in products" :key="room" class="room-card">
      <h4 class="red" :style="スタイル" @:click="modal_open = true">
        {{ room }} 1k
      </h4>
      <img :src="`/room${i}.jpg`" class="room-img" alt="" />
      <p>{{ price[i] }}万円</p>
      <button @click="increase(i)">report</button>
      <span>count :{{ counts[i] }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modal_open: false,
      メニュー: ["Home", "Shop", "About"],
      price: [60, 70, 80],
      スタイル: "color:blue",
      products: ["伏見", "浄心", "浅間町"],
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
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  height: 300px;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  text-align: center;
  width: 500px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-card {
  width: 500px;
}
.room-img {
  width: 100%;
  aspect-ratio: 4 / 3;
  object-fit: cover;
  display: block;
}
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: #2c3e50;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
