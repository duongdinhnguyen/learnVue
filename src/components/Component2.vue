<script lang="ts" setup>
    import { reactive } from "vue";
    import Component3 from "./Component3.vue";
    defineProps({
        name: String
    })

    const stateComponent2 = reactive({
        nameCom2: 'abc'
    })

    const emit = defineEmits(['dataCom2'])
    emit('dataCom2', stateComponent2.nameCom2)
</script>

<template>
    <div>
        Component 2: {{ name }}
        Emit: {{ stateComponent2.nameCom2 }}
    </div>
    <Component3 :name="name" @emit_c3="(data) => stateComponent2.nameCom2 = data"/>
</template>