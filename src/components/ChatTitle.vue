<template>
    <div
        class="flex px-4 h-14 border-b border-gray-300 bg-white items-center justify-between w-full"
    >
        <div class="flex flex-col">
            {{ chat.title }}
            <div class="text-sm text-gray-400">{{ membersCount }}</div>
        </div>
        <div class="flex text-gray-400 gap-4">
            <div class="cursor-pointer">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                >
                    <path
                        fill-rule="evenodd"
                        d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                        clip-rule="evenodd"
                    />
                </svg>
            </div>
            <div class="cursor-pointer" v-if="chat.vc">
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
                        d="M7 8h10M7 12h4m1 8l-4-4H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-3l-4 4z"
                    />
                </svg>
            </div>
            <div class="cursor-pointer" :class="{'text-blue-400': chat.type === 'channel'}">
               <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">
                  <g><rect fill="none" height="24" width="24"/><g><path d="M2,4v16h20V4H2z M20,8.67h-2.5V6H20V8.67z M17.5,10.67H20v2.67h-2.5V10.67z M4,6h11.5v12H4V6z M17.5,18v-2.67H20V18H17.5z"/></g></g>
                </svg>
            </div>
            <div class="cursor-pointer">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                >
                    <path
                        d="M10 6a2 2 0 110-4 2 2 0 010 4zM10 12a2 2 0 110-4 2 2 0 010 4zM10 18a2 2 0 110-4 2 2 0 010 4z"
                    />
                </svg>
            </div>
        </div>
    </div>
</template>
<script>
import { computed } from "vue"

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
        }
    },
}
</script>