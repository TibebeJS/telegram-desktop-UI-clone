<template>
  <div class="flex h-screen">
    <Sidebar />
    <ChatList />
    <Chat/>
    <EmojiSideBar/>
  </div>
</template>

<script>
import ChatList from './components/ChatList.vue'
import Sidebar from './components/Sidebar.vue'
import Chat from './components/Chat.vue'
import EmojiSideBar from './components/EmojiSideBar.vue'

export default {
  name: 'App',
  components: {
    ChatList,
    Sidebar,
    Chat,
    EmojiSideBar
}
}
</script>
