<template>
    <div class="border-gray-300 border-l w-80 h-full flex flex-col max-h-full">
        <div
            class="uppercase flex items-center justify-around border-gray-300 border-b text-sm text-gray-400 flex-shrink-0"
        >
            <div
                class="h-14 border-b-2 border-blue-400 text-blue-400 flex items-center justify-center w-full cursor-pointer"
            >Emoji</div>
            <div class="h-14 flex items-center w-full justify-center cursor-pointer">Stickers</div>
            <div class="h-14 flex items-center w-full justify-center cursor-pointer">gifs</div>
        </div>

        <div class="overflow-y-auto">
            <div class="flex flex-wrap justify-around w-full p-2">
                <EmojiButton v-for="emoji in recentEmojis" :emoji="emoji" :key="emoji" />
            </div>
            <div class="flex flex-wrap justify-around w-full p-2">
                <div class="text-gray-400 w-full p-2">People</div>
                <EmojiButton v-for="emoji in peopleEmojis" :emoji="emoji" :key="emoji" />
            </div>
        </div>
        <div
            class="flex flex-shrink-0 px-4 h-12 justify-between bg-gray-50 gap-3 items-center text-gray-400 w-full uppercase border-t border-gray-200 cursor-pointer"
        >
            <div v-for="category in categories" :key="category.id">
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    class="h-6 w-6"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    v-html="category.iconPath"
                    :class="{ 'text-blue-400': category.isSelected }"
                />
            </div>
        </div>
    </div>
</template>
<script>
import { reactive } from "vue"
import EmojiButton from "./EmojiButton.vue"

export default {
    setup() {

        const recentEmojis = reactive([
            "🙂", "🤪", "🤨", "🧐", "🤓", "😎", "🥸", "🤩", "😫", "😩", "🥺", "😢", "😑", "😬", "🙄", "🤤", "😪", "😮", "💨", "😵", "😵", "💫", "🤐", "🥴", "🤢", "🤮", "👿", "👹", "👺", "🤡", "🤖", "🎃", "😺", "😸", "😹", "😻", "😼", "😽", "🙀", "😿", "😾", "🤲", "👐", "🙌", "🦾", "😌", "😍", "🥰", "😘", "😗", "😙", "😚", "😋", "😛"
        ])

        const peopleEmojis = reactive([
            "😀", "😃", "😄", "😁", "😆", "😅", "😂", "🤣", "🥲", "😊", "😇", "🙂", "🙃", "😉", "😌", "😍", "🥰", "😘", "😗", "😙", "😚", "😋", "😛", "😝", "😜", "🤪", "🤨", "🧐", "🤓", "😎", "🥸", "🤩", "🥳", "😏", "😒", "😞", "😔", "😟", "😕", "🙁", "😣", "😖", "😫", "😩", "🥺", "😢", "😭", "😤", "😠", "😡", "🤬", "🤯", "😳", "🥵", "🥶", "😶", "😱", "😨", "😰", "😥", "😓", "🤗", "🤔", "🤭", "🤫", "🤥", "😶", "😐", "😑", "😬", "🙄", "😯", "😦", "😧", "😮", "😲", "🥱", "😴", "🤤", "😪", "😮", "💨", "😵", "😵", "💫", "🤐", "🥴", "🤢", "🤮", "🤧", "😷", "🤒", "🤕", "🤑", "🤠", "😈", "👿", "👹", "👺", "🤡", "💩", "👻", "💀", "👽", "👾", "🤖", "🎃", "😺", "😸", "😹", "😻", "😼", "😽", "🙀", "😿", "😾", "🤲", "👐", "🙌", "🦾", "🦿", "💄", "💋", "👄", "🦷", "👅", "👣", "👁", "👀", "🫀", "🫁", "🧠", "🗣", "👤", "👥", "🫂", "🪢", "🧶", "🧵", "🪡", "🧥", "🥼", "🦺", "👚", "👕", "👖", "🩲", "🩳", "👔", "👗", "👙", "🩱", "👘", "🥻", "🩴", "🥿", "👠", "👡", "👢", "👞", "👟", "🥾", "🧦", "🧤", "🧣", "🎩", "🧢", "👒", "🎓", "🪖", "👑", "💍", "👝", "👛", "👜", "💼", "🎒", "🧳", "👓", "🕶"
        ]);
        return {
            recentEmojis,
            peopleEmojis,
            categories: [
                {
                    id: 1,
                    iconPath: `
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
`,
                    isSelected: true,
                },
                {
                    id: 2,
                    iconPath: `
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
`
                },
                {
                    id: 3,
                    iconPath: `
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18.364 5.636l-3.536 3.536m0 5.656l3.536 3.536M9.172 9.172L5.636 5.636m3.536 9.192l-3.536 3.536M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-5 0a4 4 0 11-8 0 4 4 0 018 0z" />
`
                },
                {
                    id: 4,
                    iconPath: `                    
  <path d="M9 17a2 2 0 11-4 0 2 2 0 014 0zM19 17a2 2 0 11-4 0 2 2 0 014 0z" />
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h1m8-1a1 1 0 01-1 1H9m4-1V8a1 1 0 011-1h2.586a1 1 0 01.707.293l3.414 3.414a1 1 0 01.293.707V16a1 1 0 01-1 1h-1m-6-1a1 1 0 001 1h1M5 17a2 2 0 104 0m-4 0a2 2 0 114 0m6 0a2 2 0 104 0m-4 0a2 2 0 114 0" />
                    `
                },
                {
                    id: 5,
                    iconPath: `
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z" />
                    `
                },
                {
                    id: 6,
                    iconPath: `
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
`
                },
                {
                    id: 7,
                    iconPath: `
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z" />
                    `
                },
            ],
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