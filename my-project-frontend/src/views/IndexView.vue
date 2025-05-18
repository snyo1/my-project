<script setup>
import {logout} from "@/net";
import router from "@/router/index.js";

function userLogout(){
  console.log('开始退出登录')
  logout(() =>{
    console.log('退出成功，准备导航到登录页')
    router.push('/')})
}
</script>

<template>
  <div>
    <el-button @click="userLogout">退出登录</el-button>
  </div>
</template>

<style scoped>

</style>