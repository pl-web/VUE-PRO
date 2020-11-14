<template>
  <div>
    <input :type="type" :value="value" @input="onInput" />
  </div>
</template>

<script>
  export default {
    name: "Input",
    inject: ['form'],
    props: {
      value: {
        type: String,
        required: true,
        default: "",
      },
      type: {
        type: String,
        required: false,
        default: "text"
      }
    },
    methods: {
      onInput: function() {
        
      }
    }
  }
</script>
