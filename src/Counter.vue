<template>
    <div>
        <button @click="increment">
            Button
        </button>
        <div>{{ counter }}</div>
        <div>{{ arrayOfStars }}</div>
    </div>
</template>

<script>
import { ref, onMounted, watch, computed } from 'vue'

export default {
    props: {
        star: { type: String, default: '⭐' }
    },
    setup(props) {
        console.log(props.star)
        
        onMounted(() => {
            console.log(`Counter component has been mounted!`)
        })

        const counter = ref(1)
        const increment = () => counter.value++

        watch(counter, current => {
            if (current === 5) console.log('You have clicked five times!');
        })

        const arrayOfStars = computed(() =>
            Array.from(new Array(counter.value), () => props.star).join(' ')
        )

        return { counter, increment, arrayOfStars }
    }
}
</script>

<style>
div {
    text-align: center;
    width: 200px;
}
</style>