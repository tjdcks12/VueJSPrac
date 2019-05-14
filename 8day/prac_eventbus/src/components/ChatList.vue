<template>
<div>
  <div class="list-group">
    <template v-for="chat in chatList">
      <ChatListItem :chat="chat" @click="itemClick"/>
    </template>
  </div>
</div>
</template>

<script>
import ChatListItem from './ChatListItem';

export default {
  props: ['chatList'],
  components: {
    ChatListItem
  },
  methods: {
    itemClick(chatItem) {
      this.$emit('read-item', chatItem)
    }
  }
}
</script>
