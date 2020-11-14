<template>
  <div>
    <Form>
      <FormItem label="用户名">
        <Input v-model="user.username" />
      </FormItem>
      <FormItem label="密码">
        <Input v-model="user.password" type="password" />
      </FormItem>
      <FormItem>
        <button>Click Submit</button>
      </FormItem>
    </Form>
  </div>
</template>

<script>
  import Form from "./Form"
  import FormItem from "./FormItem"
  import Input from "./Input"
  export default {
    name: "Index",
    components: {
      Form,
      FormItem,
      Input
    },
    data() {
      return {
        user: {
          username: "",
          password: "",
        },
        rules: {
          username: [],
          password: []
        }
      }
    }
  }
</script>

<style scoped>

</style>