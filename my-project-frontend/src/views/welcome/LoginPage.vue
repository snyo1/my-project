<script setup>
import { User,Lock } from '@element-plus/icons-vue'
import {reactive ,ref} from "vue";
import {login} from "@/net";
import router from "@/router/index.js";

const formRef = ref()

const form = reactive({
  username: '',
  password: '',
  remember: false
})

const rule ={
  username: [
    {required: true, message: '请输入用户名'}
  ],
  password: [
    {required: true, message: '请输入密码'}
  ]
}

function userLogin(){
  console.info("snyo")
  formRef.value.validate((valid) =>{
    if(valid){
      login(form.username, form.password, form.remember,
          () => router.push('/index'))
    }
  })
}
</script>

<template>
  <div style="text-align: center;margin: 0 20px">
    <div style="margin-top: 150px">
      <div style="font-size: 25px;font-weight: bold">登录</div>
      <div style="font-size: 14px;color: grey">在进入系统之前，请先输入用户名和密码进行登录</div>
    </div>
    <div style="margin-top: 50px">
      <el-form :model ="form" :rules="rule" ref="formRef">
        <el-form-item prop="username">
          <el-input v-model="form.username" maxlength="10" type="text" placeholder="用户名或邮箱">
            <template #prefix>
              <el-icon><User/></el-icon>
            </template>
          </el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input v-model="form.password" type="password" maxlength="20" placeholder="密码">
            <template #prefix>
              <el-icon><Lock /></el-icon>
            </template>
          </el-input>
        </el-form-item>
        <el-row>
          <el-col :span="12" style="text-align: left">
            <el-form-item prop="remember">
              <el-checkbox v-model="form.remember" label="记住我"/>
            </el-form-item>
          </el-col>
          <el-col :span="12" style="text-align: right">
            <el-link>忘记密码？</el-link>
          </el-col>
        </el-row>
      </el-form>
    </div>
    <div style="margin-top: 40px">
      <el-button @click="userLogin()" style="width: 270px" type="success" plain>立即登录</el-button>
    </div>
    <el-divider>
      <span style="font-size: 13px;color: grey" >没有账号</span>
    </el-divider>
    <div>
      <el-button style="width: 270px" type="warning" plain>立即注册</el-button>
    </div>
  </div>
</template>

<style scoped>

</style>