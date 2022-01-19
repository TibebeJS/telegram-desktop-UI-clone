<template>
    <div class="flex flex-col h-screen">
        <ChatTitle :chat="chat" class="flex-shrink-0"></ChatTitle>
        <PinnedItems :chat="chat" class="flex-shrink-0"></PinnedItems>
        <div class="flex-grow overflow-y-auto gap-1">
            <div class="flex" v-for="message in messages" :key="`message_id_${message.id}`">
                <div class="flex flex-col justify-end pl-4 pr-2 pb-1" v-if="chat.type !== 'channel'">
                    <img
                        v-if="chat.profileImage"
                        :src="chat.profileImage"
                        :alt="`${chat.title} profile image`"
                        class="w-8 h-8 rounded-full"
                    />
                </div>
                <TextMessage :message="message" :class="{'pl-4' : chat.type === 'channel'}"/>
            </div>
        </div>
        <MuteUnmute class="flex-shrink-0" v-if="chat.type === 'channel'"/>
        <ChatForm class="flex-shrink-0" v-else></ChatForm>
    </div>
</template>
<script>
import ChatTitle from "./ChatTitle.vue";
import PinnedItems from "./PinnedItems.vue";
import MuteUnmute from "./MuteUnmute.vue";
import TextMessage from "./TextMessage.vue";
import { computed } from "vue";
import ChatForm from "./ChatForm.vue";
export default {
    props: ["chat"],
    setup(props) {
        const messages = computed(() => new Array(100).fill(undefined).map((_, i) => {
            return {
                id: i,
                type: "text",
                text: `
                Happening Now
<br/>

<a href="https://t.me/CodeNight?videochat=e4fbf7033600aa0129">https://t.me/CodeNight?videochat=e4fbf7033600aa0129</a>
                `,
                chat: props.chat,
            }
        }))

        return {
            messages
        }
    },
    components: { ChatTitle, PinnedItems, MuteUnmute, TextMessage, ChatForm }
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