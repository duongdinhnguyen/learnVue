<script setup lang="ts">
    defineProps<{
        todos: Array<Object>
    }>()
</script>

<template>
    <ul>
        <li v-for="(todo, index) in todos" :key="index">{{ todo }}</li>
    </ul>
</template>