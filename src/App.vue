<script setup lang="ts">
  import { computed, reactive} from "vue"
  import TodoList from "./views/TodoList.vue"

  const state = reactive({
    todo: '',
    todoCheckbox: [],
    todos: []
  })

  function addTodo() {
    state.todos.push(state.todo)
    state.todo = ''
  }

  function removeTodo(todo) {
    state.todos = state.todos.filter((item, index) => item != todo)
  }

  // const todoCheckbox = computed(() => {
  //   console.log(state); 
  // })

  function deleteTodoCheckbox () {
    state.todos = state.todos.filter((todo, index) => state.todoCheckbox.indexOf(todo) == -1)
    state.todoCheckbox = []
  }

  function checkboxAll () {
    state.todoCheckbox = state.todos
  }

</script>

<template>
  <div>
    <div>
      <input type="text" v-model="state.todo">
      <button @click="addTodo">Add Todo</button>
      <button @click="deleteTodoCheckbox">Xóa các mục đã chọn</button>
    </div>
    <div>
      <button @click="checkboxAll">Chọn tất cả</button>
    </div>
  
    <div>
      <ul>

        <li 
          v-for="(todo, index) in state.todos" :key="index"
        >
          <input type="checkbox" name="todo-name" :id="'todo-check-box' + index" v-model="state.todoCheckbox" :value="todo">
          <label :for="'todo-check-box' + index">{{ todo }}</label> 
          <button @click="removeTodo(todo)">x</button>
        </li>
    </ul>
    </div>
  </div>
</template>