<template>
  <div class="login">
    <div class="form">
      <p class="title">欢迎登录云管理微聊系统</p>
      <el-form label-position="top" label-width="100px" :model="loginForm" style="margin-top: 60px; padding: 0 65px" :rules="rules" ref="loginFormRef">
        <el-form-item label="账号" prop="account">
          <el-input v-model="loginForm.account" />
        </el-form-item>
        <el-form-item label="密码" prop="password">
          <div class="flex-between">
            <el-input style="flex:1;width: 313px;margin-right: 14px" type="password" v-model="loginForm.password" />
            <el-link>忘记密码？</el-link>
          </div>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" style="width: 100%;height: 50px;margin-top: 30px;border-radius: 25px" @click="sumbit">登录</el-button>
        </el-form-item>
        <el-form-item>
          <el-link style="margin: 0 auto">新用户注册</el-link>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>
<script setup>
import { reactive, ref } from 'vue'
import { useRouter } from 'vue-router'
const router = useRouter()

const loginForm = reactive({
  account: '',
  password: '',
})
const loginFormRef = ref()
const rules = reactive({
  account: [{ required: true, message: '请输入账号', trigger: 'blur' }],
  password: [{ required: true, message: '请输入密码', trigger: 'blur' }],
})

const sumbit = async () => {
  router.push('/home')
  await loginFormRef.value.validate((valid, fields) => {
    if (valid) {
      console.log('submit!')
    } else {
      console.log('error submit!', fields)
    }
  })
}
</script>
<style lang="scss" scoped>
.login {
  background: url(@/static/bg.jpg);
  width: 100vw;
  height: 100vh;
  min-width: 1024px;
  min-height: 768px;
  @include flex-middle;
  .form {
    width: 542px;
    height: 606px;
    border-radius: 16px;
    background-color: rgba(29, 57, 101, 0.75);
    .title {
      color: rgba(255, 255, 255, 1);
      font-size: 28px;
      line-height: 130px;
      border-bottom: 1px solid rgba(151, 151, 151, 1);
      text-align: center;
    }
    :deep(.el-link) {
      color: white;
    }
    :deep(.el-form-item__label) {
      color: white;
    }
    :deep(.el-input__wrapper) {
      height: 48px;
      border-radius: 26px;
      padding-left: 24px;
      background-color: rgba(255, 255, 255, 0.27);
      .el-input__inner {
        color: white;
        background: none !important;
      }
    }
  }
}
</style>