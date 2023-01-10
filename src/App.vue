<script lang="ts" setup>
  import Component2 from "./components/Component2.vue";
  import { reactive, ref } from "vue";

  const state = reactive({
    name: "Đương Đình Nguyễn"
  })

  const dataChild = ref('initial value')

  function getDataFromChild(data) {
    console.log(dataChild.value)
    dataChild.value = data
    console.log(dataChild.value)
    
  }


</script>

<template>
  <div>
    {{ state.name }}
  </div>
  <Component2 :name="state.name" @data-com2="(data) =>state.name=data" :getDataFromChild="getDataFromChild"/>
</template>