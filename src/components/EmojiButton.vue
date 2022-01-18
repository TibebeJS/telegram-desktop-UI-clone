<template>
    <div class="flex items-center justify-center h-11 w-11 hover:bg-gray-200 text-lg cursor-pointer">{{ emoji }}</div>
</template>
<script>
export default {
    props: ["emoji"],
    setup() {

    },
}
</script>