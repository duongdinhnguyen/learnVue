<script setup lang="ts">
    import { reactive } from "vue";

    defineProps<{
        todos: Array<String>,
        todoCheckbox: Array<String>,
        removeTodo: Function
    }>()
</script>

<template>
    <ul>
        <li 
          v-for="(todo, index) in todos" :key="index"
        >
          <input type="checkbox" name="todo-name" :id="'todo-check-box' + index"  :value="todo">
          <label :for="'todo-check-box' + index">{{ todo }}</label> 
          <button @click="removeTodo(todo)">x</button>
        </li>
    </ul>
</template>