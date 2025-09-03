<template>
  <div class="discount">
    <h4>今購入すると{{ discountValue }}割引</h4>
  </div>
</template>
<script>
export default {
  name: "Discount",
  props: {
    discount: "Number",
  },
  data() {
    return {
      discountValue: this.discount,
    };
  },
  mounted() {
    setInterval(() => {
      if (this.discountValue > 0) {
        this.discountValue -= 1;
      }
    }, 1000);
  },
};
</script>
<style></style>
