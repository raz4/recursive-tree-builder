<template>
  <div id="app">
    <div class="tree-title">Recursive Tree Builder</div>
    <TreeLevel :root="root"/>
  </div>
</template>

<script>
import TreeLevel from './components/TreeLevel.vue'

export default {
  name: 'app',
  components: {
    TreeLevel
  },
  data() {
    return {
      root: [
        {title: 'Root1', data: '--', id: 1, children: [
          {title: 'Node2', data: 'Child of Root1', id: 3, children: [
            {title: 'Node5', data: 'Child of Node2', id: 6, children: []},
            {title: 'Node6', data: 'Child of Node2', id: 7, children: []}
          ]},
          {title: 'Node3', data: 'Child of Root1', id: 4, children: [
            {title: 'Node4', data: 'Child of Node3', id: 5, children: []}
          ]},
          {title: 'Node7', data: 'Child of Root1', id: 8, children: []}
        ]}
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.tree-title {
  font-size: 32px;
  padding-bottom: 20px;
}
</style>
