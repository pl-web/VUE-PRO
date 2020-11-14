<template>
  <div id="operator-group">
    <span
      v-for="(item, index) in operator"
      :key="index"
      :class="'operator-button' + index"
      :style="{ width: width + 'px' }"
      @click="toHandleOperator(item)"
    >
      {{ item }}
    </span>
  </div>
</template>

<script>
export default {
  name: "Operator",
  inject: ["form"],
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
  computed: {
    getFirstNumber() {
      return this.form.model.firstNumber
    },
    getSecondNumber() {
      return this.form.model.secondNumber
    }
  },
  methods: {
    toHandleOperator(item) {
      switch (item) {
        case "加":
          this.add();
          break;
        case "减":
          this.substract();
          break;
        case "乘":
          this.multiply();
          break;
        default:
          this.divide();
      }
    },
    add() {},
    substract() {},
    multiply() {},
    divide() {},
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