<template>
  <div id="app">
    <Index></Index>
  </div>
</template>

<script>
// import Index from './components/Index.vue'
// import Index from './form/Index.vue' // 进行计算的例子
import Index from './FormComponent/Index.vue' // 表单提交的例子
export default {
  name: 'App',
  components: {
    Index
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
