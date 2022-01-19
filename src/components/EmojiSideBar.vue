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