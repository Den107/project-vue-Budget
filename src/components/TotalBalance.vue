<template>
  <div class="total-value" :class="classObj">Balance: {{ total }}</div>
</template>

<script>
export default {
  name: "TotalBalance",
  props: {
    total: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    classObj() {
      return {
        positive: this.total > 0,
        negative: this.total < 0,
        neutral: this.total === 0,
      };
    },
  },
};
</script>

<style scoped>
.total-value {
  font-size: 26px;
  text-transform: uppercase;
  padding: 20px;
  text-align: center;
}
.positive {
  color: green;
}
.negative {
  color: crimson;
}
.neutral {
  color: black;
}
</style>