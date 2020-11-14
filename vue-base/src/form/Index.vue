<template>
  <div id="main-page">
    <FormItem label="请输入第一个数字">
      <Input v-model="firstNumber" />
    </FormItem>
    <FormItem label="请输入第二个数字">
      <Input v-model="firstNumber" />
    </FormItem>
    <FormItem label="请选择运算符号">
      <Operator :operator="operateSymbol"></Operator>
    </FormItem>
    <FormItem label="两数字计算结果为">
      <div id="operate-result">{{ result }}</div>
    </FormItem>
  </div>
</template>

<script>
import Input from "./Input";
import Operator from "./Operator";
import FormItem from "./FormItem";
export default {
  name: "Index",
  components: {
    Input,
    Operator,
    FormItem,
  },
  data() {
    return {
      firstNumber: "",
      secondNumber: "",
      operateSymbol: ["加", "减", "乘", "除"],
      result: "",
    };
  },
};
</script>

<style scoped>
#operate-result {
  width: 500px;
  height: 25px;
  border: 2px solid #000;
  line-height: 25px;
  color: rgb(0, 0, 0);
}
#main-page {
  
}
</style>