<template>
  <div id="app">
    <Header :new-message-count="newMessageCount">
    </Header>

    <div class="container mx-auto mt-5">
      <ChatList :chat-list="chatList" @read-item="readChatItem">
        test
      </ChatList>
    </div>
  </div>
</template>

<script>
import ChatList from './components/ChatList';
import Header from './components/Header';

export default {
  name: 'app',
  data() {
    return {
      chatList: [
        {
          id: 1,
          lastMessage: '채팅 메시지1',
          new: 1
        },
        {
          id: 2,
          lastMessage: '채팅 메시지2',
          new: 2
        },
        {
          id: 13,
          lastMessage: '채팅 메시지3',
          new: 3
        },
      ]
    }
  },
  computed: {
    newMessageCount() {
      return this.chatList.map(item => item.new).reduce((a,b) => a+b);
    }
  },
  methods : {
    readChatItem(chatItem) {
      this.chatList.filter(item => item.id === chatItem.id)[0].new = 0;
    }
  },
  components: {
    Header,
    ChatList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
