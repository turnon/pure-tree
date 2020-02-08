<template>
  <ul class="pure-tree-root">
    <node :node="root"></node>
  </ul>
</template>

<script>
  import node from "./node.vue"

  export default {
    props: ["root"],
    components: {
      node
    }
  }
</script>

<style scoped>
  .pure-tree-root {
    margin: 0;
    padding: 0;
  }
</style>
