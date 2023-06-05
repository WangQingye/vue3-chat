<template>
  <el-row class="header" align="middle" style="padding: 0 38px">
    <el-col :span="3">
      <div class="flex-middle" style="float:left">
        <img class="logo" src="@/static/bg.jpg" />
        <div class="left">
          <p class="name">全购网络</p>
          <p class="url">I2F2F.COM</p>
        </div>
      </div>
    </el-col>
    <el-col :span="18" class="title">欢迎登录云管理微聊系统</el-col>
    <el-col :span="3">
      <img class="right-logo" src="@/static/bg.jpg" />
    </el-col>
  </el-row>
</template>
<script setup>
defineProps({
  msg: {
    type: String,
  },
})
</script>
<style scoped scss>
.header {
  width: 100%;
  height: 60px;
  background-color: rgba(56, 61, 74, 1);
  box-shadow: 0px 2px 10px 0px rgba(0, 0, 0, 0.46);
  color: white;
  .title {
    line-height: 60px;
    text-align: left;
  }
  .logo {
    width: 38px;
    height: 38px;
    margin-right: 8px;
  }
  .right-logo {
    width: 36px;
    height: 36px;
    margin-right: 8px;
    float: right;
    border-radius: 50%;
  }
  .left {
    .name {
      font-size: 16px;
    }
    .url {
      color: rgba(132, 132, 132, 1);
      font-size: 10px;
    }
  }
}
</style>
