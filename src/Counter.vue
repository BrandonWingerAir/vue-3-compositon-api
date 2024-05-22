<template>
    <div>
        <button>
            Button
        </button>
    </div>
</template>

<script>
import { onMounted } from 'vue'

export default {
    props: {
        emoji: { type: String, default: '⭐' }
    },
    setup(props) {
        console.log(props.emoji);
        
        onMounted(() => {
            console.log(`Counter component has been mounted!`);
        })
    }
}
</script>