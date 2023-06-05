<template>
  <div class="chat-window">
    <div class="left">
      <div class="top">
        <el-input placeholder="搜索联系人/聊天记录" v-model="serachText" @keydown.enter="search">
          <template #prefix>
            <span class="icon iconfont icon-search" style="color:#999"></span>
          </template>
        </el-input>
      </div>
      <div class="list">
        <el-collapse v-model="activeNames" @change="handleChange">
          <el-collapse-item title="全部消息" name="1">
            <template #title>
              <span class="title flex-middle">全部消息<span class="icon iconfont icon-xiala" :class="[activeNames == 1 ? 'active' : '']"></span></span>
            </template>
            <div class="list-wrapper">
              <ChatItem v-for="(item,index) in chatItems" :key="index" :item="item" :active="activeId == item.id" />
            </div>
          </el-collapse-item>
        </el-collapse>
      </div>
    </div>
    <div class="middle">
      <ChatFrame />
    </div>
  </div>
</template>
<script setup>
import { Search } from '@element-plus/icons-vue'
import { reactive, ref } from 'vue'
import { ElMessage } from 'element-plus'
import ChatItem from './components/ChatItem.vue'
import ChatFrame from './components/ChatFrame.vue'
const serachText = ref('')
const activeId = ref(1)
const chatItems = ref([
  {
    type: 0,
    from: '全购网络有限公司',
    name: '用户12321321312',
    newText: '您好！',
    time: '19:23',
    newNum: 0,
    id: 1,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '花落罗刷就',
    newText: '您好！您好！您好！您好！您好！您好！您好！您好！您好！',
    time: '19:23',
    newNum: 11,
    id: 2,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
  {
    type: 1,
    from: '蜀山区门店',
    name: '你停风在吹',
    newText: '您好！',
    time: '19:23',
    newNum: 100,
    id: 3,
  },
])
const search = () => {
  ElMessage.success('search')
}
const activeNames = ref('1')
</script>
<style scoped lang="scss">
.chat-window {
  // width: 1080px;
  height: calc(100% - 48px);
  width: 100%;
  background-color: white;
  display: flex;
  .left {
    width: 28%;
    border-right: 1px solid #f5f5f5;
    height: 100%;
    .top {
      padding: 8px 16px;
      border-bottom: 1px solid #f5f5f5;
    }
    .list {
      height: calc(100% - 48px);
      .title {
        color: rgba(51, 51, 51, 1);
        font-size: 16px;
        padding: 16px;
      }
      .icon {
        color: #666;
        font-size: 12px;
        margin-left: 8px;
        display: inline-block;
        transform: rotate(0deg);
        transition: all 0.5s ease;
      }
      .active {
        transform: rotate(-180deg);
      }
      .list-wrapper {
        overflow: auto;
        height: 500px;
      }
    }
    :deep(.el-collapse) {
      color: white;
      border: none;
      .el-collapse-item__header {
        color: #ddeaff;
      }
      .el-collapse-item__header,
      .el-collapse-item__wrap {
        background: none;
        border: none;
      }
      .el-collapse-item__arrow {
        display: none;
      }
    }
  }
  .middle {
    flex: 1;
  }
}
</style>