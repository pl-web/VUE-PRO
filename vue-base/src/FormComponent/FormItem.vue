<template>
  <div>
    <label v-if="label">{{ label }}</label>
    <slot></slot>
    <span class="__error__message__" v-if="error">{{ error }}</span>
  </div>
</template>

<script>
  export default {
    name: "FormItem",
    props: {
      label: {
        type: String,
        default: "",
        required: false
      },
      error: {
        type: String,
        default: "",
        required: false
      }
    }
  }
</script>

<style scoped>
.form-item {
  margin-top: 10px;
  display: flex;
}
label {
  margin-right: 10px;
}
.__error__message__ {
  font-size: 10px;
  line-height: 100%;
  margin-top: 9px;
  margin-left: 5px;
  color: rgb(226, 21, 21);
}
</style>