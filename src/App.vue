<script lang="ts" setup>
  import Component2 from "./components/Component2.vue";
  import { reactive } from "vue";

  const state = reactive({
    name: "Đương Đình Nguyễn"
  })
</script>

<template>
  <div>
    {{ state.name }}
  </div>
  <Component2 :name="state.name" @data-com2="(data) =>state.name=data"/>
</template>