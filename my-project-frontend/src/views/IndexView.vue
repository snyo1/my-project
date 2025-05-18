<script setup>
import {logout} from "@/net";
import router from "@/router/index.js";

function uesrLogout(){
  logout(() => router.push('/'))
}
</script>

<template>
  <div>
    <el-button @click="uesrLogout">退出登录</el-button>
  </div>
</template>

<style scoped>

</style>