
<template>
  <header>
    <form @submit.prevent="onSubmit">
      <button v-on:click="increment">{{ state.count }}</button>
      <span v-html="state.rawHtml"></span>
      <span v-bind="state.elementAttribute">v-bind</span>
      <button type="submit">Submit</button>
    </form>
  </header>
</template>

<script lang="ts" setup>
  import { reactive } from "vue";

  const state = reactive({
    count: 0,
    title: "Đây là title",
    rawHtml: `<span style="color: red">This should be red.</span>`,
    elementAttribute: {
      data: 1,
      title: 'title Attribute'
    }
  })
  
  function increment() {
    state.count ++
  }
  function onSubmit() {
    console.log(12222)
  }

  function mounted() {
    console.log(12345)
  }
</script>