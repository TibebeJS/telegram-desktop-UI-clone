<template>
    <div
        class="w-full h-full flex items-center justify-center"
        :style="{
            backgroundImage: 'url(' + bgPattern + ')',
            backgroundSize: 'cover',
        }"
    >
        <div class="bg-gray-600 bg-opacity-40 rounded-full text-white text-xs py-1 px-3">Select a chat to start messaging</div>
    </div>
</template>
<script>
export default {
    setup() {
        return {
            bgPattern: new URL(`../assets/chat_bg1.png`, import.meta.url).href
        }
    },
}
</script>