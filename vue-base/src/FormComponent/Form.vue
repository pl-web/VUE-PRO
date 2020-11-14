<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
  export default {
   name: "Form",
   provide() {
     return {
       form: this
     }
   },
   props: {
     model: {
       type: Object,
       required: true
     },
     rules: {
       type: Object,
       required: false
     }
   }
  }
</script>

<style scoped>

</style>