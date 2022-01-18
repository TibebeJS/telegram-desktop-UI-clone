<template>
  <div class="border-gray-300 border-r w-72 h-full flex flex-col">
    <ChatSearch class="h-16" />

    <div class="flex-grow overflow-y-scroll h-screen" style="scrollbar-width: thin;">
      <ChatItem
        v-for="chat in chats"
        :chat="chat"
        :key="chat.id"
        @click="selectChat(chat)"
        :is-selected="selectedChat == chat.id"
      />
    </div>
  </div>
</template>
<script>
import { reactive } from "vue"
import ChatSearch from "./ChatSearch.vue"
import ChatItem from "./ChatItem.vue";

export default {
  props: ["selectedChat"],
  setup() {
    const chats = reactive([
      {
        id: "1",
        profileImage: new URL(`../assets/profile-images/code-night.jpg`, import.meta.url).href,
        title: "CodeNight",
        lastMessage: {
          text: "Last message",
          senderName: "Tibebes"
        }
      },
      {
        id: "2",
        profileImage: new URL(`../assets/profile-images/gdg-addis.jpg`, import.meta.url).href,
        title: "GDG Addis",
        lastMessage: {
          text: "Last message",
          senderName: "Tibebes"
        }
      },
      {
        id: "3",
        profileImage: new URL(`../assets/profile-images/tikvah-ethiopia.jpg`, import.meta.url).href,
        title: "TIKVAH-ETHIOPIA",
        lastMessage: {
          text: "Last message",
          senderName: "Tibebes"
        }
      },
    ]);
    return {
      chats,
    };
  },
  components: { ChatSearch, ChatItem },
  methods: {
    selectChat(chat) {
      this.$emit("chat-selected", chat.id);
    }
  }
}
</script>
<style scoped>
::-webkit-scrollbar {
  width: 10px;
  height: 8px;
}

/* Track */
::-webkit-scrollbar-track {
  border-radius: 100vh;
  background: #edf2f7;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #8e9296;
  border-radius: 100vh;
  border: 3px solid #edf2f7;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #a0aec0;
}
</style>