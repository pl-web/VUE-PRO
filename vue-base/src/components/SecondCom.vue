<template>
  <div>
    <!-- $listeners -->
    <span v-on="$listeners">SecondCom:</span>
    <input type="text" :value="msg" />
  </div>
</template>

<script>
  export default {
    // props: {
    //   msg: {
    //     type: String,
    //     default: '',
    //     required: false
    //   }
    // },
    data() {
      return {
        msg: ''
      }
    },
    mounted() {
      // this.$eventbus.$on("getMessage", (msg) => {
      //   this.msg = msg
      // });
      this.$parent.$on("getMessage", (msg) => {
        this.msg = msg
      });
    }
  }
</script>