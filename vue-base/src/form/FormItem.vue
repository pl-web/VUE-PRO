<template>
  <div class="form-item">
    <label v-if="label">{{ label }}</label>
    <slot></slot>
    <div v-if="error">{{ error }}</div>
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
      }
    },
    data () {
      return {
        error: '', // 如果为空，代表校验通过
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
</style>