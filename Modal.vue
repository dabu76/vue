<template>
  <div class="black-bg" v-if="modal_open === true">
    <div class="white-bg">
      <h4>{{ ルーム[push].title }}</h4>
      <img :src="`${ルーム[push].image}`" style="width: 100%" alt="" />
      <p>{{ ルーム[push].content }}</p>
      <input v-model="month" />
      <p>{{ month }}ヶ月選択しました : {{ ルーム[push].price * month }}円</p>
      <button @click="$emit('closeModal')">閉じる</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "Modal",
  data() {
    return {
      month: 1,
    };
  },
  props: {
    ルーム: "Array",
    push: "Number",
    modal_open: "boolean",
  },
  emits: ["closeModal"],
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
  height: 500px;
}
</style>
