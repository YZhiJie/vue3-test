<template>
  <div class="home">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <el-input />
    <el-button>提交</el-button>
  </div>
</template>

<script>
import { getCurrentInstance } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import clonedeep from 'lodash.clonedeep'
import ElementPlus from 'element-plus'
import 'element-plus/dist/index.css'

export default {
  name: 'App',
  data() {
    return {
      name: 'zhangsan'
    }
  },
  components: {
    HelloWorld,
  },
  created() {
    const o = {
      a: 1,
      b: 2,
    }
    const o2 = clonedeep(o)
    console.log(o === o2)
    // 获取当前组件实例
    const currentComponentInstance = getCurrentInstance()
    // currentComponentInstance.root.appContext.app 根实例
    currentComponentInstance.root.appContext.app.use(ElementPlus)
  },
}
</script>

<style>
.home {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
