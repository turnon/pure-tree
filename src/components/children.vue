<template>
  <ul>
    <node v-for="child in children" :node="child" />
  </ul>
</template>

<script>
  import node from "./node.vue"

  export default {
    props: ["children"],
    components: {
      node
    }
  }
</script>

<style>
</style>
