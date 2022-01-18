<template>
    <div class="px-4 flex items-end gap-4">
        <div class="bg-white w-96 flex flex-col p-3 pb-2 my-4 rounded-md divide-y">
            <div class="contents">
                <div class="text-blue-400">{{ message.chat.title }}</div>
                <div class="font-light">{{ message.text }}</div>
            </div>
            <div
                v-if="message.chat.commentsAreEnabled"
                class="flex items-center h-8 w-full justify-between pt-2 text-blue-400 text-sm"
            >
                <div class="flex gap-2">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"
                        />
                    </svg>
                    <div>Leave a comment</div>
                </div>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-5 w-5"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M9 5l7 7-7 7"
                    />
                </svg>
            </div>
        </div>
        <div class="mb-4 text-gray-400">
            <!-- <svg
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
                    d="M13 9l3 3m0 0l-3 3m3-3H8m13 0a9 9 0 11-18 0 9 9 0 0118 0z"
                />
            </svg> -->
        </div>
    </div>
</template>
<script>
export default {
    props: ["message"],
    setup() {

    },
}
</script>