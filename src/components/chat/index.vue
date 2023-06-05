<template>
  <div class="chat-wrapper">
    <ChatLeft />
    <ChatMiddle />
    <ChatRight />
  </div>
</template>
<script setup>
import ChatLeft from './components/ChatLeft.vue'
import ChatMiddle from './components/ChatMiddle.vue'
import ChatRight from './components/ChatRight.vue'
</script>
<style scoped lang="scss">
.chat-wrapper {
  display:flex;
}
</style>
