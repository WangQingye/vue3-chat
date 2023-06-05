<template>
  <div class="chat-middle">
    <ChatMiddleTop />
    <component :is="componentTag"></component>
  </div>
</template>
<script setup>
import ChatMiddleTop from './ChatMiddleTop.vue'
import ChatWindow from './chatContent/ChatWindow.vue'
import { reactive, ref } from 'vue'
const componentTag = ChatWindow
</script>
<style scoped lang="scss">
.chat-middle {
  width: 1080px;
}
</style>