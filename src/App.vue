
<template>
  <header>
    <form @submit.prevent="onSubmit">
      <button v-on:click="increment">{{ count }}</button>
      <span v-html="rawHtml"></span>
      <span v-bind="elementAttribute">v-bind</span>
      <button type="submit">Submit</button>
    </form>
  </header>
</template>

<script>
  export default {
    data() {
      return {
        count: 0,
        title: "Đây là title",
        rawHtml: `<span style="color: red">This should be red.</span>`,
        elementAttribute: {
          data: 1,
          title: 'title Attribute'
        }
      }
    },
    methods: {
      increment() {
        this.count ++
      },
      onSubmit() {
        console.log(12222)
      }

    },
    mounted() {
      console.log(12345)
    }
  }
</script>