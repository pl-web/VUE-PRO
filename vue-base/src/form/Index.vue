<template>
  <div id="main-page">
    <Form :model="model" :rules="rules">
      <FormItem label="请输入第一个数字" prop="firstNumber">
        <Input v-model="model.firstNumber" placeholder="0" />
      </FormItem>
      <FormItem label="请输入第二个数字" prop="secondNumber">
        <Input v-model="model.secondNumber" placeholder="0" />
      </FormItem>
      <FormItem label="请选择运算符号">
        <Operator :operator="model.operateSymbol"></Operator>
      </FormItem>
      <FormItem label="两数字计算结果为">
        <Input
          id="operate-result"
          v-model="model.result"
          disabled="true"
          placeholder="0"
          style="text-align: center"
        />
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
        firstNumber: [
          {
            message: "请输入正确的内容",
            type: 'number'
          }
        ],
        secondNumber: [
          {
            message: "请输入正确的内容",
            type: 'number'
          }
        ]
      }
    }
  }
};
</script>

<style scoped>
</style>