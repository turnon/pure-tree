<template>
  <div>
    <tree :msg="123"></tree>
  </div>
</template>

<script>
  import tree from "./components/pure-tree.vue"

  export default {
    components: {
      tree
    }
  }
</script>

<style>
</style>
