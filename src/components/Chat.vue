<template>
    <div class="flex flex-col">
        <ChatTitle :chat="chat"></ChatTitle>
        <PinnedItems :chat="chat"></PinnedItems>
    </div>
</template>
<script>
import ChatTitle from "./ChatTitle.vue";
import PinnedItems from "./PinnedItems.vue";
export default {
    props: ["chat"],
    setup() {
    },
    components: { ChatTitle, PinnedItems }
}
</script>