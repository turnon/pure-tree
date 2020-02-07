<template>
  <div>
    <tree :root="root"></tree>
  </div>
</template>

<script>
  import tree from "./components/pure-tree.vue"

  export default {
    components: {
      tree
    },
    data() {
      return {
        root: {
          key: "a",
          value: "a",
          children: [{
            key: "b",
            value: "b",
            children: [{
              key: "d",
              value: "d"
            }, {
              key: "e",
              value: "e"
            }]
          }, {
            key: "c",
            value: "c"
          }]
        }
      }
    }
  }
</script>

<style>
</style>
