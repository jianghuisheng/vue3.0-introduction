<template>
  <div id="nav">
    <h1>{{ name }}---{{ age }}---{{ n }}</h1>
    <button @click="changeAge()">按钮</button>
  </div>
  <!-- <router-view/> -->
</template>

<script>
import axios from 'axios'
import { reactive, toRefs, computed, onMounted } from 'vue'
export default {
  setup() {
    // 创建响应式的数据 reactive
    const state = reactive({
      // 响应式 data
      name: 'hello',
      age: 18,
      n: computed(() => state.age + 1), // 计算属性
      cur: 1,
      items: [],
    })
    let changeAge = () => {
      // 函数的定义 method
      console.log(111)
      state.age++
    }
    let getList = () => {
      axios({
        method: 'get',
        url: 'http://www.baidu.com',
      })
        .then(res => {
          console.log(res)
          // let {code,result} = res.data
          // if(code == '200'){
          //   items = res.data.result
          // }
        })
        .catch(error => {
          console.log(error)
        })
    }
    onMounted(() => {
      // 生命周期 钩子函数 挂载完成
      getList()
    })
    // 供template
    return {
      // ...state, // 取消响应特性
      ...toRefs(state), // 保持双向特性
      changeAge,
      getList,
    }
  },
}
</script>

<style lang="scss">
// @import './assets/css/index.css'
.down {
  transform: rotate(180deg);
}
.up {
  transform: rotate(0deg);
}
</style>
