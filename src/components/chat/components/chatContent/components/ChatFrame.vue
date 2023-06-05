<template>
  <div class="chat-frame">
    <div class="top flex-between">
      <p class="name">{{ item.name }}</p>
      <p>
        <span class="icon iconfont icon-shouye-zhihui" style="color:#999"></span>
        {{ item.from }}
      </p>
    </div>
    <div class="list">
      <div v-for="chat in chatList" :key="chat.time">
        <p class="time">{{ chat.time }}</p>
        <div :class="['chat', talk.from == 1 ? 'chat-right' : '']" v-for="(talk,index) in chat.list" :key="index">
          <img class="avatar" src="@/static/bg.jpg" />
          <p class="text" v-if="talk.type == 'text'">{{ talk.text }}</p>
          <div class="contract" v-if="talk.type == 'contract'">
            <div class="contract-top flex-between">
              <span class="icon iconfont icon-hetongdingdan"></span>
              <span class="contract-name ellipsis"> {{ talk.name }}</span>
            </div>
            <div class="contract-bottom flex-between">
              <span class="bottom-text">仅支持移动端打开签署</span>
              <span class="icon iconfont icon-erweima" style="color:#999"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { reactive, ref } from 'vue'
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

const chatList = ref([
  {
    time: '10:59',
    list: [
      {
        type: 'text',
        text: '你好，请问下商品什么时候发货？',
        from: 0,
      },
      {
        type: 'text',
        text: '您好',
        from: 1,
      },
      {
        type: 'contract',
        name: '合同名称合同名称',
        from: 1,
      },
    ],
  },
])
</script>
<style scoped lang="scss">
.chat-frame {
  .top {
    background-color: rgba(255, 255, 255, 1);
    padding: 14px 20px;
    color: rgba(51, 51, 51, 1);
    font-size: 16px;
    border-bottom: 1px solid rgba(212, 212, 212, 1);
    .name {
      color: rgba(30, 30, 30, 1);
      font-size: 20px;
    }
  }
  .list {
    padding: 20px 30px;
    .time {
      color: rgba(153, 153, 153, 1);
      font-size: 14px;
      text-align: center;
      margin-bottom: 10px;
    }
    .chat {
      display: flex;
      margin-bottom: 30px;
      .avatar {
        width: 42px;
        height: 42px;
        border-radius: 4px;
        margin-right: 16px;
      }
      .text {
        min-height: 42px;
        border-radius: 12px;
        border: 1px solid rgba(216, 216, 216, 1);
        padding: 11px 20px;
      }
      .contract {
        border-radius: 4px;
        background-color: rgba(255, 255, 255, 1);
        box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.19);
        width: 201px;
        height: 86px;
        .contract-top {
          padding: 7px 10px;
          border-bottom: 1px solid rgba(237, 237, 237, 1);
          .icon {
            font-size: 48px;
            color: #8486f8;
            margin-right: 8px;
          }
          .contract-name {
            color: rgba(30, 30, 30, 1);
            font-size: 14px;
            flex: 1;
          }
        }
        .contract-bottom {
          padding: 5px 10px;
          .bottom-text {
            color: rgba(153, 153, 153, 1);
            font-size: 12px;
          }
        }
      }
    }
    .chat-right {
      justify-content: flex-end;
      .avatar {
        order: 999;
        margin-left: 16px;
      }
      .text {
        border: none;
        background-color: rgba(141, 185, 255, 1);
      }
    }
  }
}
</style>