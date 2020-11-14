<template>
  <div>
    组件之间的通讯
    <FirstCom info="this info from index"></FirstCom>
    <SecondCom @click="handleClick"></SecondCom> 
  </div>
</template>

<script>
import FirstCom from './FirstCom.vue'
import SecondCom from './SecondCom.vue'
export default {
  provide() {
    return {
      info: 'info content',
      that: this,
    }
  },
  components: {
    FirstCom,
    SecondCom
  },
  methods: {
    handleClick() {
      console.log('this info from index');
    }
  }
};
</script>