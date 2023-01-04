<script setup>
import { reactive} from "vue";
    const state = reactive({ count: 0 })
    function onSubmit() {
      console.log(state.count)
    }

    function increment() {
      state.count ++
    }
    
</script>

<template>
  <header>
    <form @submit.prevent="onSubmit">
      <button v-on:click="increment">{{ state.count }}</button>
      <br>
      <button type="submit">Submit</button>
    </form>
  </header>
</template>

