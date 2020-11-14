<template>
  <div class="form-box">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Form",
  props: {
    // rules
    rules: {
      type: Object,
      required: false,
    },
    // model
    model: {
      type: Object,
      required: true,
    },
  },
  provide() {
    return {
      form: this,
    };
  }
};
</script>

<style scoped>
</style>