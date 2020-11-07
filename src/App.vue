<template>
  <div id="app">
    {{msg}}
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {

  },
  data() {
    return {
      todos: [
        {id: 1, title: 'Todo 1', completed: false},
        {id: 1, title: 'Todo 2', completed: true},
        {id: 1, title: 'Todo 3', completed: false}
      ]
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>
