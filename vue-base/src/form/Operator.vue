<template>
  <div id="operator-group">
    <span
      v-for="(item, index) in operator"
      :key="index"
      :class="'operator-button' + index"
      :style="{ width: width + 'px' }"
    >
      {{ item }}
    </span>
  </div>
</template>

<script>
export default {
  name: "Operator",
  props: {
    operator: {
      type: Array,
      required: true,
      default: [],
    },
    width: {
      type: Number,
      required: false,
      default: 30,
    },
  },
};
</script>

<style scoped>
#operator-group {
  height: 25px;
}
span {
  display: inline-block;
  height: 30px;
  padding: 0;
  margin: 0;
  margin-left: 20px;
  line-height: 30px;
  color: #FFF;
  cursor: pointer;
}
.operator-button0 {
  background-color: #1aa;
}
.operator-button1 {
  background-color: rgb(17, 114, 170);
}
.operator-button2 {
  background-color: rgb(170, 142, 17);
}
.operator-button3 {
  background-color: rgb(170, 17, 76);
}
</style>