<template>
  <div class="chat-middle-top flex-middle">
    <div class="left flex-middle">
      <img class="logo" src="@/static/bg.jpg" />
      <span>全购网络有限公司</span>
      <span class="icon iconfont icon-icon_change"></span>
    </div>
    <div class="middle flex-middle">
      <div class="flex-middle">
        <span class="icon iconfont icon-hetongdingdan" style="margin-right: 8px;"></span>
        <span class="icon iconfont icon-kefufill"></span>
      </div>
      <span class="icon iconfont icon-shouqi"></span>
    </div>
  </div>
</template>
<script setup>
</script>
<style scoped lang="scss">
.chat-middle-top {
  width: 1080px;
  height: 48px;
  background-color: rgba(239, 240, 241, 1);
  justify-content: space-between !important;
  padding: 0 16px;
  .icon {
    cursor: pointer;
    &:hover {
      opacity: 0.7;
    }
  }
  .left {
    color: rgba(51, 51, 51, 1);
    font-size: 16px;
    span {
      color: #333333;
      margin: 0 8px;
    }
    .logo {
      width: 24px;
      height: 24px;
    }
    .icon {
      font-size: 14px;
      color: #1770fe;
    }
  }
  .middle {
    padding: 0 16px;
    font-size: 20px;
    flex: 1;
    justify-content: space-between !important;
    .icon {
      color: #727272;
    }
  }
}
</style>