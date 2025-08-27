<template>
  <div v-for="(room, i) in ルーム" :key="room" class="room-card">
    <h4 class="red" :style="スタイル" @click="$emit('openModal', i)">
      {{ room.title }} 1k
    </h4>
    <img :src="`${room.image}`" class="room-img" alt="" />
    <p>{{ room.price }}万円</p>
    <button @click="increase(i)">report</button>
    <span>count :{{ counts[i] }}</span>
  </div>
</template>
<script>
export default {
  name: "Click",
  props: {
    counts: { type: Number, required: true },
    ルーム: { type: Array, required: true },
    push: { type: Number, required: true },
    modal_open: { type: Boolean, required: true },
    increase: { type: Function, required: true },
  },
  data() {
    return { スタイル: "color:blue" };
  },
  emits: ["openModal"],
};
</script>
<style></style>
