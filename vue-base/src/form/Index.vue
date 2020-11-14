<template>
  <div id="main-page">
    <Form :model="model" :rules="rules">
      <FormItem label="请输入第一个数字">
        <Input v-model="model.firstNumber" />
      </FormItem>
      <FormItem label="请输入第二个数字">
        <Input v-model="model.secondNumber" />
      </FormItem>
      <FormItem label="请选择运算符号">
        <Operator :operator="model.operateSymbol"></Operator>
      </FormItem>
      <FormItem label="两数字计算结果为">
        <div id="operate-result">{{ model.result }}</div>
      </FormItem>
    </Form>
  </div>
</template>

<script>
import Input from "./Input";
import Operator from "./Operator";
import FormItem from "./FormItem";
import Form from "./Form";
export default {
  name: "Index",
  components: {
    Input,
    Operator,
    FormItem,
    Form,
  },
  data() {
    return {
      model: {
        firstNumber: "",
        secondNumber: "",
        operateSymbol: ["加", "减", "乘", "除"],
        result: "",
      },
     rules: {
       
     }
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