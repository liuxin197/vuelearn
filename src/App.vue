<template>
  <div>
    <ul>
      <li v-for="item in list">{{ item }}</li>
    </ul>
    <button @click="add">添加</button>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive, proxyRefs } from "vue";
// ref,reactive
// ref 支持所有的类型 reactive 引用类型 Array Object Map Set
// ref 取值 赋值 都需要加.value reactive 是不需要.value
// reactive proxy 不能直接赋值 否则破坏响应式对象
// 解决方案 数组可以使用push 加解构
let list = reactive<string[]>([]);

const add = () => {
  setTimeout(() => {
    let res = ["EDG", "RNG", "JDG"];
      list.push(...res);
    console.log(list);
    
  }, 2000);
};
// git test
</script>
<style scoped></style>
