<template>
  <input :type="type" :value="value" @input="onInput">
</template>

<script>
  export default {
    name: "Input",
    props: {
      value: {
        type: String,
        default: ""
      },
      type: {
        type: String,
        default: "text",
        required: false
      }
    },
    methods: {
      onInput: function(e) {
        // emit event
        this.$emit("input", e.target.value);
      }
    }
  }
</script>

<style scoped>
input {
  width: 500px;
  height: 25px;
  border: 2px solid #000;
  text-indent: 10px;
  vertical-align: middle;
}
</style>