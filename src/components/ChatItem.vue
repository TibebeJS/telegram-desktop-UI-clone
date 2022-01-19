<template>
    <div
        class="px-4 flex gap-2 h-16 items-center cursor-pointer"
        :class="[isSelected ? 'bg-blue-300' : 'hover:bg-gray-200']"
    >
        <div class="flex-grow-0 flex-shrink-0">
            <img
                v-if="chat.profileImage"
                :src="chat.profileImage"
                :alt="`${chat.title} profile image`"
                class="w-11 h-11 rounded-full"
            />
            <div v-else></div>
        </div>
        <div class="flex flex-col w-full">
            <div
                :class="[isSelected ? 'text-white font-medium' : 'text-gray-600']"
                class="flex justify-between items-center w-full text-sm"
            >
                <div class="flex gap-1 items-center">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-3 w-3"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                        v-if="chat.type === 'channel'"
                    >
                        <path
                            fill-rule="evenodd"
                            d="M18 3a1 1 0 00-1.447-.894L8.763 6H5a3 3 0 000 6h.28l1.771 5.316A1 1 0 008 18h1a1 1 0 001-1v-4.382l6.553 3.276A1 1 0 0018 15V3z"
                            clip-rule="evenodd"
                        />
                    </svg>
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-3 w-3"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                        v-else-if="chat.type === 'group'"
                    >
                        <path
                            d="M13 6a3 3 0 11-6 0 3 3 0 016 0zM18 8a2 2 0 11-4 0 2 2 0 014 0zM14 15a4 4 0 00-8 0v3h8v-3zM6 8a2 2 0 11-4 0 2 2 0 014 0zM16 18v-3a5.972 5.972 0 00-.75-2.906A3.005 3.005 0 0119 15v3h-3zM4.75 12.094A5.973 5.973 0 004 15v3H1v-3a3 3 0 013.75-2.906z"
                        />
                    </svg>
                    <div class="font-medium">{{ chat.title }}</div>
                </div>
                <div class="flex-grow-0">8:15 AM</div>
            </div>
            <div class="text-sm w-full flex" :class="[isSelected ? 'text-white' : 'text-gray-400']">
                <div class="flex-grow">
                    <span
                        :class="[isSelected ? 'text-white' : 'text-blue-300']"
                    >{{ chat.lastMessage.senderName }}:</span>
                    {{ chat.lastMessage.text }}
                </div>
                <div class="flex-grow-0 bg-gray-300 flex items-center font-medium rounded-full px-2 text-xs" :class="[isSelected ? 'text-blue-400' : 'text-white']">
                    {{ Math.floor(Math.random() * 2000 )}}
                </div>
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