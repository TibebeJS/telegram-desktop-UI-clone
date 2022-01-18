<template>
  <div class="flex h-screen">
    <Sidebar />
    <ChatList />
    <div class="w-auto flex-grow">
      <Chat v-if="selectedChat" :chat="selectedChat" />
      <ChatPlaceholder v-else></ChatPlaceholder>
    </div>
    <EmojiSideBar />
  </div>
</template>

<script>
import ChatList from './components/ChatList.vue'
import Sidebar from './components/Sidebar.vue'
import Chat from './components/Chat.vue'
import EmojiSideBar from './components/EmojiSideBar.vue'

import { reactive } from 'vue'
import ChatPlaceholder from './components/ChatPlaceholder.vue'

export default {
  name: 'App',
  components: {
    ChatList,
    Sidebar,
    Chat,
    EmojiSideBar,
    ChatPlaceholder
  },
  setup() {
    let selectedChat = reactive(null)

    return { selectedChat }
  }
}
</script>
