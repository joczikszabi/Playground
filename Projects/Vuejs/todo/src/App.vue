<template>
  <div>
    <app-header v-bind:title="title"></app-header>
    <app-todos @on-delete="onDelete" v-bind:todos="todos"></app-todos>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Todos from './components/Todos'

export default {
  components: {
    'app-header':Header,
    'app-todos':Todos
  },

  data() {
    return {
      title: 'ToDo App',
      todos:
          [
            {
              'id': 0,
              'name': 'Finish YouTube Vuejs tutorial videos',
              'isDone': true
            },
            {
              'id':1,
              'name':'Finish Vue Todo List Project',
              'isDone': false
            },
            {
              'id':2,
              'name':'Learn Machine Learning with Les',
              'isDone': false
            }
          ]
    }
  },

  methods: {
    onDelete(id) {
      this.todos = this.todos.filter(x => {
        return x.id != id;
      })
    }
  }
}
</script>

<style>
  body {
    margin: 0;
  }
</style>
