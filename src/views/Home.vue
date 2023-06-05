<template>
  <div class="home">
    <MyHeader />
    <div class="flex-middle wrapper">
      <Chat />
    </div>
  </div>
</template>
<script setup>
import { reactive, ref } from 'vue'
import { useRouter } from 'vue-router'
import MyHeader from '@/components/Header.vue'
import Chat from '@/components/chat/index.vue'
const router = useRouter()
</script>
<style lang="scss" scoped>
.home {
  background: url(@/static/bg.jpg);
  width: 100vw;
  height: 100vh;
  min-width: 1024px;
  min-height: 768px;
  .wrapper {
    height: calc(100% - 60px);
  }
}
</style>