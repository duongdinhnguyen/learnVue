
<template>
  <header>
    <button @click="count++">{{ count }}</button>
  </header>
</template>

<script>
  export default {
    data() {
      return {
        count: 0
      }
    }
  }
</script>