<template>
    <div class="flex flex-col">
        <ChatTitle :chat="chat"></ChatTitle>
    </div>
</template>
<script>
import ChatTitle from "./ChatTitle.vue";
export default {
    props: ["chat"],
    setup() {
    },
    components: { ChatTitle }
}
</script>