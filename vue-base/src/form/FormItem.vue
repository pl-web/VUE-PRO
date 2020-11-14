<template>
  <div class="form-item">
    <label v-if="label">{{ label }}</label>
    <slot></slot>
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