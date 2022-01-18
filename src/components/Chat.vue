<template>
    <div class="flex flex-col h-screen">
        <ChatTitle :chat="chat"></ChatTitle>
        <PinnedItems :chat="chat"></PinnedItems>
        <div class="flex-grow h-full overflow-y-auto gap-4">
            <template v-for="message in messages" :key="`message_id_${message.id}`">
                <TextMessage :message="message" />
            </template>
        </div>
        <MuteUnmute />
    </div>
</template>
<script>
import ChatTitle from "./ChatTitle.vue";
import PinnedItems from "./PinnedItems.vue";
import MuteUnmute from "./MuteUnmute.vue";
import TextMessage from "./TextMessage.vue";
export default {
    props: ["chat"],
    setup(props) {
        const messages = new Array(100).fill(undefined).map((_, i) => {
            return {
                id: i,
                type: "text",
                text: "test message",
                chat: props.chat,
            }
        })

        return {
            messages
        }
    },
    components: { ChatTitle, PinnedItems, MuteUnmute, TextMessage }
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