# pure-tree

A Vue tree component using pure css to implement fold and expand

## Usage

```
<template>
  <div id="app">
    <tree :root="top"></tree>
  </div>
</template>

<script>
  import tree from '@ken_yuan/pure-tree'
  import '@ken_yuan/pure-tree/dist/pure-tree.css'

  export default {
    name: 'app',
    components: {
      tree
    },
    data() {
      return {
        top: {
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
```