<template>
  <div>
    <input :type="type" :value="value" @input="onInput" v-bind="$attrs" />
  </div>
</template>

<script>
  export default {
    name: "Input",
    inheritAttrs: false, // 避免继承来自Input的属性内容
    props: {
      value: {
        type: String | Number,
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
        this.$parent.$emit("validate", e.target.value)
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
#operate-result {
  width: 500px;
  height: 25px;
  border: 2px solid #000;
  line-height: 25px;
  color: rgb(0, 0, 0);
  text-align: center !important;
}
</style>