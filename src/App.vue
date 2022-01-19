<template>
  <div class="flex h-screen">
    <Sidebar :selected-folder="selectedFolder.data" @folder-selected="updateSelectedFolder"/>
    <ChatList
      :selected-chat="selectedChat.chat ? selectedChat.chat : {}"
      @chatSelected="updateSelectedChat"
      :chats="chats"
      :loading-chats="loadingChats"
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
    <EmojiSideBar v-if="selectedChat.chat && selectedChat.chat.type !== 'channel'"></EmojiSideBar>
    <ChannelInfo
      v-else-if="selectedChat.chat && selectedChat.chat.type === 'channel'"
      :chat="selectedChat.chat"
    ></ChannelInfo>
  </div>
</template>

<script>
import ChatList from './components/ChatList.vue'
import Sidebar from './components/Sidebar.vue'
import Chat from './components/Chat.vue'
import EmojiSideBar from './components/EmojiSideBar.vue'

import { reactive, ref } from 'vue'
import ChatPlaceholder from './components/ChatPlaceholder.vue'
import ChannelInfo from './components/ChannelInfo.vue'

export default {
  name: 'App',
  components: {
    ChatList,
    Sidebar,
    Chat,
    EmojiSideBar,
    ChatPlaceholder,
    ChannelInfo
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
        commentsAreEnabled: true,
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
        commentsAreEnabled: false,
      },
    ]);

    const loadingChats = ref(true)

    setTimeout(() => {
      loadingChats.value = false;
    }, Math.floor(Math.random() * 3) * 1000)


    const selectedFolder = reactive({
      data: {}
    })

    return {
      selectedChat,
      bgPattern: new URL(`./assets/chat-bg.jpg`, import.meta.url).href,

      chats,

      loadingChats,
      selectedFolder,

      updateSelectedChat(chatId) {
        let chat = chats.find(chat => chat.id == chatId)
        selectedChat.chat = chat
      },
      updateSelectedFolder(folder) {
        selectedFolder.data = folder
      },
    }
  },
}
</script>
