<script lang="ts" setup>
    import { ref } from 'vue';

    defineProps({
        name: String
    })
    
    const emit = defineEmits(['emit_c3', 'emitc3'])
    const dataComponent3 = ref(500)
    emit('emit_c3', dataComponent3.value)
    

    function getDataComponent3() {
        return emit('emit_c3', Math.random())
    }
</script>

<template>
    <div>
        Component 3 : {{ name }}
        <button @click="$emit('emit_c3', Math.random())">Click</button>
    </div>
</template>