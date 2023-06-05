<template>
  <div :class="['chat-item', active ? 'active-item' : '']">
    <div class="top">
      <span class="icon iconfont icon-shouye-zhihui" style="color:#999"></span>
      [{{ item.type == 0 ? '门店' : '企业' }}]消息来自<span class="from-name">{{ item.from }}</span>
    </div>
    <div class="middle flex-middle">
      <img class="logo" src="@/static/bg.jpg" />
      <div class="info">
        <p class="name ellipsis">{{ item.name }}</p>
        <p class="text ellipsis">{{ item.newText }}</p>
      </div>
      <div class="right">
        <p class="time">{{ item.time }}</p>
        <span v-show="item.newNum > 0" class="new-num">{{ item.newNum>99 ? '99+' : item.newNum}}</span>
      </div>
    </div>
  </div>
</template>
<script setup>
defineProps({
  item: {
    type: Object,
    default: {
      type: 0,
      from: '全购网络有限公司',
      name: '用户12321321312',
      newText: '您好！',
      time: '19:23',
      newNum: 11,
    },
  },
  active: {
    type: Boolean,
    default: false,
  },
})
</script>
<style scoped lang="scss">
.chat-item {
  color: rgba(176, 176, 176, 1);
  font-size: 12px;
  padding: 14px 16px;
  border-bottom: 1px solid #f5f5f5;
  cursor: pointer;
  &:hover {
    background: #e0e2e471;
  }
  .top {
    .from-name {
      font-weight: bold;
    }
    .icon {
      font-size: 12px;
    }
  }
  .middle {
    width: 100%;
    .logo {
      width: 42px;
      height: 42px;
      border-radius: 4px;
    }
    .info {
      flex: 1;
      margin: 0 10px;
      .name {
        color: rgba(30, 30, 30, 1);
        font-size: 16px;
      }
      .text {
        max-width: 140px;
      }
    }
    .right {
      .new-num {
        line-height: 18px;
        color: white;
        font-size: 12px;
        border-radius: 9px;
        background-color: rgba(255, 82, 25, 1);
        padding: 0 8px;
      }
    }
  }
}
.active-item {
  background: #e0e2e4;
}
</style>