<template>
    <div class="px-4 flex gap-2 h-16 items-center cursor-pointer"
        :class="[ isSelected ? 'bg-blue-300' : 'hover:bg-gray-200' ]"
    >
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
            <div :class="[ isSelected ? 'text-white font-medium' : 'text-gray-600']">
                {{ chat.title }}
            </div>
            <div class="text-sm" :class="[ isSelected ? 'text-white' : 'text-gray-400']">
                <span :class="[ isSelected ? 'text-white' : 'text-blue-300']">{{ chat.lastMessage.senderName }}:</span> {{ chat.lastMessage.text}}
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: ["chat", "isSelected"],
    setup() {

    },
}
</script>