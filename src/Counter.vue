<template>
    <div>
        <button @click="increment">
            Button
        </button>
        <div>{{ counter }}</div>
    </div>
</template>

<script>
import { ref, onMounted } from 'vue'

export default {
    props: {
        emoji: { type: String, default: '⭐' }
    },
    setup(props) {
        console.log(props.emoji)
        
        onMounted(() => {
            console.log(`Counter component has been mounted!`)
        })

        const counter = ref(0)
        const increment = () => counter.value++

        return { counter, increment }
    }
}
</script>