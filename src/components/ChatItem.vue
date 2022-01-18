<template>
    <div class="px-4 flex gap-2">
        <div>
            <img
                v-if="chat.profileImage"
                :src="chat.profileImage"
                :alt="`${chat.title} profile image`"
                class="w-11 h-11 rounded-full"
            />
            <div v-else></div>
        </div>
        <div class="flex flex-col">
            <div>
                {{ chat.title }}
            </div>
            <div class="text-gray-400">
                {{ chat.lastMessage }}
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: ["chat"],
    setup() {

    },
}
</script>