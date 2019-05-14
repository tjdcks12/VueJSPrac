<template>
  <div id="app">
    <Header :new-message-count="newMessageCount">
    </Header>
    <div class="container mx-auto mt-5">
      <ChatList :chat-list="chatList" @read-item="readChatItem"></ChatList>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ChatList from './components/ChatList.vue'
import { bus } from './event-bus';

export default {
  name: 'app',
  created() {
    bus.$on('CHAT_CLICK', chat => {
      this.readChatItem(chat);
    });
  },
  data() {
    return {
      chatList : [
        {
          id:1,
          new:2,
          lastMessage:'안녕하세요'
        },
        {
          id:2,
          new:1,
          lastMessage:'안녕하세요2'
        },
        {
          id:3,
          new:4,
          lastMessage:'안녕하세요3'
        },
      ]
    }
  },
  computed: {
    newMessageCount() {
      return this.chatList.map(item => item.new).reduce((a,b) => a+b);
    }
  },
  methods:
  {
    readChatItem(chatItem) {
      this.chatList.filter(item => item.id === chatItem.id)[0].new = 0;
    }
  },
  components: {
    Header, ChatList
  }
}
</script>
