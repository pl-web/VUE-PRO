<template>
  <div style="margin-bottom: 10px; margin-top: 10px">
    <span>FirstCom:</span>
    <button @click="sendMessage">Send Message</button>
    <div style="">{{ $attrs.info }}</div>
    <input type="text" :value="info">
  </div>
</template>

<script>
export default {
  inject: ['info', 'that'],
  data() {
    return {
      msg: 'From FirstCom'
    }
  },
  methods: {
    sendMessage () {
      // this.$eventbus.$emit("getMessage", this.msg)
      this.$parent.$emit("getMessage", this.msg)
    }
  }
};
</script>