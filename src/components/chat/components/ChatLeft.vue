<template>
  <div class="chat-left">
    <el-collapse v-model="activeNames" @change="handleChange">
      <el-collapse-item title="协同办公" name="1">
        <span class="icon iconfont icon-xiaoxi-zhihui"></span>
        <span class="icon iconfont icon-fenxiang"></span>
      </el-collapse-item>
      <el-collapse-item title="客服聊天" name="2">
        <span class="icon iconfont icon-xiaoxi-zhihui icon-active"></span>
        <span class="icon iconfont icon-sr_jingdong"></span>
        <span class="icon iconfont icon-taobao-circle-fill"></span>
        <span class="icon iconfont icon-douyin"></span>
      </el-collapse-item>
      <el-collapse-item title="其他设置" name="3">
        <span class="icon iconfont icon-kandian-zhihui"></span>
      </el-collapse-item>
    </el-collapse>
  </div>
</template>
<script setup>
import { reactive, ref } from 'vue'
const activeNames = ref(['1','2','3'])
</script>
<style scoped lang="scss">
.chat-left {
  width: 101px;
  height: 684px;
  background-color: rgba(29, 57, 101, 1);
  border-radius: 10px 0 0 10px;
  padding: 30px 10px;
  .icon {
    display: block;
    font-size: 24px;
    margin: 0 auto;
    color: #80a5df;
    text-align: center;
    cursor: pointer;
    &:hover {
      color: #ddeaff;
    }
  }
  .icon-active {
    color: white;
  }
  :deep(.el-collapse) {
    color: white;
    border: none;
    .el-collapse-item__header {
      color: #ddeaff;
      border: none;
    }
    .el-collapse-item__header,
    .el-collapse-item__wrap {
      background: none;
    }
    .el-collapse-item__wrap {
      border-bottom: 1px solid #2F5289;
    }
    .el-collapse-item__arrow {
      order: -1;
      font-size: 10px;
      margin: 0;
      margin-right: 8px;
    }
  }
}
</style>
