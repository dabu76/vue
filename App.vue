<template>
  <Modal
    :ルーム="ルーム"
    :push="push"
    :modal_open="modal_open"
    @closeModal="
      () => {
        modal_open = false;
      }
    "
  />
  <div class="container">
    <div class="menu">
      <a v-for="作名 in メニュー" :key="作名">{{ 作名 }}</a>
    </div>
    <Discount />
    1kショップ
    <Click
      :ルーム="ルーム"
      :counts="counts"
      :modal_open="modal_open"
      :increase="increase"
      @openModal="
        (i) => {
          modal_open = true;
          push = i;
        }
      "
    />
  </div>
</template>

<script>
import data from "./assets/oneroom.js";
import Discount from "./discount.vue";
import Modal from "./Modal.vue";
import Click from "./Click.vue";
export default {
  name: "App",
  data() {
    return {
      push: 0,
      ルーム: data,
      modal_open: false,
      メニュー: ["Home", "Shop", "About"],
      price: [60, 70, 80],
      スタイル: "color:blue",
      products: ["伏見", "浄心", "浅間町"],
      counts: [0, 0, 0, 0, 0, 0],
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
  components: {
    Discount: Discount,
    Modal: Modal,
    Click: Click,
  },
};
</script>

<style>
.discount {
  background: #eee;
  width: 500px;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
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
  height: 500px;
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
