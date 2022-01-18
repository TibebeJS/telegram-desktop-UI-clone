<template>
    <div class="border-gray-300 border-l w-80 h-full flex flex-col max-h-full bg-gray-200 gap-3">
        <div class="p-4 flex flex-col gap-4 bg-white">
            <div class="w-full justify-between flex">
                <div>Channel Info</div>
                <div>
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                    >
                        <path
                            fill-rule="evenodd"
                            d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                            clip-rule="evenodd"
                        />
                    </svg>
                </div>
            </div>

            <div class="w-full flex gap-4">
                <div>
                    <img
                        v-if="chat.profileImage"
                        :src="chat.profileImage"
                        :alt="`${chat.title} profile image`"
                        class="w-20 h-20 rounded-full border"
                    />
                    <div v-else></div>
                </div>
                <div class="flex flex-col pt-4">
                    <div>{{ chat.title }}</div>
                    <div class="text-sm text-gray-400">{{ membersCount }}</div>
                </div>
            </div>
        </div>

        <div class="overflow-y-auto bg-white">
            
        </div>
        <div class="overflow-y-auto bg-white">
            
        </div>
    </div>
</template>
<script>
import { computed } from "vue"
import EmojiButton from "./EmojiButton.vue"

export default {
    props: ["chat"],
    setup(props) {
       return {
            membersCount: computed(() => {
                const suffixText = props.chat.type === "channel" ? "subscribers" : "members"

                const formatNumber = (x) => {
                    let result = ""

                    for (let i = 0; i < x.length; i++) {
                        let a = x.length - 1 - i

                        result += x[i] + (a % 3 === 0 && a != 0 ? "," : "")
                    }

                    return result
                }

                return `${formatNumber(String(props.chat.membersCount))} ${suffixText}`
            })
        };
    },
    components: {
        EmojiButton,
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