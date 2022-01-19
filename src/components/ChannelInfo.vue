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

        <div class="overflow-y-auto bg-white flex flex-col">
            <div class="flex p-5">
                <div class="text-gray-400 w-12 p-1">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-6 w-6"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                        />
                    </svg>
                </div>
                <div class="flex flex-col text-sm gap-4">
                    <div class="flex flex-col">
                        <div
                            class="text-blue-400 hover:underline cursor-pointer"
                        >https://t.me/tikvahethiopia</div>
                        <div class="text-gray-400">Link</div>
                    </div>
                    <div class="flex flex-col">
                        <div class="text-gray-700 font-normal">Addis Ababa, Ethiopia</div>
                    </div>
                    <div class="flex flex-col">
                        <div
                            class="text-blue-400 hover:underline cursor-pointer"
                        >https://twitter.com/tikvahethiopia?s=09</div>
                    </div>
                    <div class="flex flex-col">
                        <div class="text-blue-400 hover:underline cursor-pointer">@tikvahuniversity</div>
                        <div
                            class="text-blue-400 hover:underline cursor-pointer"
                        >@tikvahethAfaanOromoo</div>
                        <div class="text-blue-400 hover:underline cursor-pointer">@tikvahethmagazine</div>
                        <div class="text-blue-400 hover:underline cursor-pointer">@tikvahethsport</div>
                        <div class="text-gray-400 pt-1">Description</div>
                    </div>
                </div>
            </div>
            <hr class="ml-16" />
            <div class="flex p-5 items-center">
                <div class="text-gray-400 w-12 p-1">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-6 w-6"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
                        />
                    </svg>
                </div>
                <div class="flex flex-col text-sm text-gray-700 gap-4 flex-grow">Notifications</div>
                <div class="text-gray-400 p-1">
                    <label for="toogleA" class="flex items-center cursor-pointer">
                        <!-- toggle -->
                        <div class="relative">
                            <!-- input -->
                            <input id="toogleA" type="checkbox" class="sr-only" />
                            <!-- line -->
                            <div class="w-7 h-3 bg-gray-400 rounded-full shadow-inner"></div>
                            <!-- dot -->
                            <div
                                class="dot absolute w-5 h-5 border-2 bg-white border-gray-400 rounded-full shadow -left-1 -top-1 transition"
                            ></div>
                        </div>
                    </label>
                </div>
            </div>
        </div>
        <div class="overflow-y-auto py-5 bg-white flex flex-col">
            <div class="flex items-center px-6 h-11 hover:bg-gray-200 cursor-pointer">
                <div class="text-gray-400 w-12 p-1">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
</svg>
                </div>
                <div class="text-gray-700 text-sm">
                    36727 photos
                </div>
            </div>
            <div class="flex items-center px-6 h-11 hover:bg-gray-200 cursor-pointer">
                <div class="text-gray-400 w-12 p-1">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
</svg>
                </div>
                <div class="text-gray-700 text-sm">
                    910 videos
                </div>
            </div>
            <div class="flex items-center px-6 h-11 hover:bg-gray-200 cursor-pointer">
                <div class="text-gray-400 w-12 p-1">
                   <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 21h10a2 2 0 002-2V9.414a1 1 0 00-.293-.707l-5.414-5.414A1 1 0 0012.586 3H7a2 2 0 00-2 2v14a2 2 0 002 2z" />
</svg>
                </div>
                <div class="text-gray-700 text-sm">
                    130 files
                </div>
            </div>
            <div class="flex items-center px-6 h-11 hover:bg-gray-200 cursor-pointer">
                <div class="text-gray-400 w-12 p-1">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1" />
</svg>
                </div>
                <div class="text-gray-700 text-sm">
                    1896 shared links
                </div>
            </div>
            <div class="flex items-center px-6 h-11 hover:bg-gray-200 cursor-pointer">
                <div class="text-gray-400 w-12 p-1">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11a7 7 0 01-7 7m0 0a7 7 0 01-7-7m7 7v4m0 0H8m4 0h4m-4-8a3 3 0 01-3-3V5a3 3 0 116 0v6a3 3 0 01-3 3z" />
</svg>
                </div>
                <div class="text-gray-700 text-sm">
                    141 voice messages
                </div>
            </div>
            
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

input:checked ~ .dot {
    transform: translateX(100%);
    background-color: #48bb78;
}
</style>