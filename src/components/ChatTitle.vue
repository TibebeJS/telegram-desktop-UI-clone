<template>
    <div class="flex flex-col h-16 border-b border-gray-300 bg-white justify-center px-4">
        {{ chat.title }}
        <div class="text-sm text-gray-400">{{ membersCount }}</div>
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