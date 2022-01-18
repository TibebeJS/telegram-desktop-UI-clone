<template>
<div class="w-full h-full" :style="{
    backgroundImage: 'url(' + bgPattern + ')',
    backgroundSize: 'cover',
}">
    <div>Select a chat to start messaging</div>
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