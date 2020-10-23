<template>
  <div>
    <app-todoItem @on-delete="onDelete" v-for="todo in todos" :key="todo.id" v-bind:todo="todo"></app-todoItem>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
  name: "Header",
  props:{
    'todos': Array
  },
  components: {
    'app-todoItem': TodoItem
  },
  methods: {
    onDelete(id) {
      this.$emit('on-delete', id)
    }
  }
}
</script>

<style scoped>
  div {
    display: flex;
    flex-flow: column;
  }
</style>