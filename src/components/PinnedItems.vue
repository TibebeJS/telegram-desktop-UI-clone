<template>
    <div
        class="flex px-2 h-14 border-b border-gray-300 bg-white items-center justify-between w-full"
    >
        <div class="flex gap-1 px-2">
            <div class="flex flex-col justify-between">
                <div class="h-2 bg-blue-100 w-1"></div>
                <div class="h-2 bg-blue-100 w-1"></div>
                <div class="h-2 bg-blue-400 w-1"></div>
            </div>
            <div class="flex flex-col text-blue-400 text-xs">
                <div>Pinned Message</div>
                <div class="text-black">{{ pinnedMessage }}</div>
            </div>
        </div>
        <div class="flex text-gray-400">
            <div class="pr-2">
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
                        d="M8 13v-1m4 1v-3m4 3V8M8 21l4-4 4 4M3 4h18M4 4h16v12a1 1 0 01-1 1H5a1 1 0 01-1-1V4z"
                    />
                </svg>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: ["chat"],
    setup(props) {
        return {
            pinnedMessage: "Happening now"
        }
    },
}
</script>