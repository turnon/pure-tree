<template>
  <li>
    <input type="checkbox" :id="checkbox_id" />
    <label :for="checkbox_id" />
    <a>{{ node.value }}</a>
    <children v-if="node.children" :children="node.children" />
  </li>
</template>

<script>
  export default {
    props: ["node"],
    components: {
      children: () => import("./children.vue")
    },
    computed: {
      checkbox_id() {
        return `pure-tree-${this.node.key}`
      }
    }
  }
</script>

<style>
</style>
