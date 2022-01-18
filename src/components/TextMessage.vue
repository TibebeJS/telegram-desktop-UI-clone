<template>
    <div class="px-4 flex items-end gap-4">
        <div class="bg-white w-96 relative bubble flex flex-col p-3 pb-2 my-2 rounded-md divide-y">
            <div class="relative pb-4">
                <div class="text-blue-400">{{ message.chat.title }}</div>
                <div class="font-light text-sm" v-html="message.text"></div>
                <div
                    class="absolute text-gray-300 bottom-0 right-0 flex text-xs gap-2 items-center"
                >
                    <div class="flex gap-1">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="h-3 w-3"
                            viewBox="0 0 20 20"
                            fill="currentColor"
                        >
                            <path d="M10 12a2 2 0 100-4 2 2 0 000 4z" />
                            <path
                                fill-rule="evenodd"
                                d="M.458 10C1.732 5.943 5.522 3 10 3s8.268 2.943 9.542 7c-1.274 4.057-5.064 7-9.542 7S1.732 14.057.458 10zM14 10a4 4 0 11-8 0 4 4 0 018 0z"
                                clip-rule="evenodd"
                            />
                        </svg>425
                    </div>
                    <div>3:40 PM</div>
                </div>
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
            </svg>-->
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
<style scoped>
.bubble:after {
    content: " ";
    position: absolute;
    width: 0;
    height: 0;
    bottom: 0;
    left: -6px;
    border-bottom: 25px solid white;
    border-left: 20px solid transparent;
}
</style>