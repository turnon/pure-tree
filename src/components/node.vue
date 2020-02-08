<template>
  <li>
    <input type="checkbox" :id="checkbox_id" />
    <label :for="checkbox_id" />
    <a>{{ node.value }}</a>
    <ul v-if="node.children">
      <node v-for="child in node.children" :node="child" />
    </ul>
  </li>
</template>

<script>
  export default {
    name: "node",
    props: ["node"],
    computed: {
      checkbox_id() {
        return `pure-tree-${this.node.key}`
      }
    }
  }
</script>

<style>
</style>
