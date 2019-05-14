<template>
  <div id="app">
    <Header :new-message-count="newMessageCount"></Header>


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
          newMessage: 1
        },
        {
          id: 2,
          lastMessage: '채팅 메시지2',
          newMessage: 2
        },
        {
          id: 13,
          lastMessage: '채팅 메시지3',
          newMessage: 3
        },
      ]
    }
  },
  computed: {
    newMessageCount() {
      return this.chatList.map(item => item.newMessage).reduce((a,b) => a+b);
    }
  },
  methods : {
    readChatItem(chatItem) {
      this.chatList.filter(item => item.id === chatItem.id)[0].newMessage = 0;
    }
  },
  components: {
    Header,
    ChatList
  }
}
</script>
