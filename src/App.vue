<template>
  <div class="flex h-screen">
    <Sidebar />
    <ChatList
      :selected-chat="selectedChat.chat ? selectedChat.chat : {}"
      @chatSelected="updateSelectedChat"
      :chats="chats"
    />
    <div
      class="w-auto flex-grow"
      :style="{
        backgroundImage: 'url(' + bgPattern + ')',
        backgroundSize: 'contain',
      }"
    >
      <Chat v-if="selectedChat.chat" :chat="selectedChat.chat" />
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
    let selectedChat = reactive({
      chat: null
    })

    const chats = reactive([
      {
        id: "1",
        profileImage: new URL(`./assets/profile-images/code-night.jpg`, import.meta.url).href,
        title: "CodeNight",
        lastMessage: {
          text: "Last message",
          senderName: "Tibebes"
        },
        membersCount: 1490,
        type: "group",
      },
      {
        id: "2",
        profileImage: new URL(`./assets/profile-images/gdg-addis.jpg`, import.meta.url).href,
        title: "GDG Addis",
        lastMessage: {
          text: "Last message",
          senderName: "Tibebes"
        },
        membersCount: 2912,
        type: "channel",
      },
      {
        id: "3",
        profileImage: new URL(`./assets/profile-images/tikvah-ethiopia.jpg`, import.meta.url).href,
        title: "TIKVAH-ETHIOPIA",
        lastMessage: {
          text: "Last message",
          senderName: "Tibebes"
        },
        membersCount: 1224801,
        type: "channel",
      },
    ]);


    return {
      selectedChat,
      bgPattern: new URL(`./assets/chat-bg.jpg`, import.meta.url).href,

      chats,

      updateSelectedChat(chatId) {
        let chat = chats.find(chat => chat.id == chatId)
        selectedChat.chat = chat
      }
    }
  },
}
</script>
