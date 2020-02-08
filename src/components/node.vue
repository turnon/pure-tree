<template>
  <li>
    <input v-if="node.children" type="checkbox" :id="checkbox_id" />
    <label v-if="node.children" :for="checkbox_id" />
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

<style scoped>
  * {
    padding: 0;
  }

  ul {
    margin-left: 15px;
  }

  li {
    list-style-type: none;
    margin: 0px 10px;
    position: relative;
  }

  ul ul li::before {
    content: "";
    position: absolute;
    top: -7px;
    left: -28px;
    border-left: 1px dotted #ccc;
    border-bottom: 1px dotted #ccc;
    width: 15px;
    height: 15px;
  }

  li::after {
    position: absolute;
    content: "";
    top: 8px;
    left: -28px;
    border-left: 1px dotted #ccc;
    width: 15px;
    height: 100%;
  }

  li:last-child::after {
    display: none;
  }

  li a {
    padding: 2px 5px;
  }

  li a:hover,
  li a:hover+ul li a,
  li a:focus,
  li a:focus+ul li a {
    background-color: #d3d3d3;
  }

  label {
    margin: .2em 0 0 -.6em;
    position: absolute;
    border: 1px solid #ccc;
    background: white;
    width: .6em;
    height: .6em;
    display: inline-block;
    line-height: .65;
  }

  label.placeholder {
    visibility: hidden;
  }

  label::before {
    color: #ccc;
    font-family: serif;
    margin-left: 0.02em;
  }

  input[type='checkbox'] {
    margin-left: 5px;
    display: none
  }

  input[type='checkbox']:checked~ul {
    display: none
  }

  input[type="checkbox"]+label::before {
    content: '-';
  }

  input[type="checkbox"]:checked+label::before {
    content: '+';
  }
</style>
