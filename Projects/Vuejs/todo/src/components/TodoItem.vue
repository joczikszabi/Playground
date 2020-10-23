<template>
  <div>
    <span v-bind:class="{completed: todo.isDone }"> {{todo.name}} </span>
    <button v-on:click="onDelete">Delete</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todo: Object
  },
  data() {
    return {

    }
  },
  methods: {
    onDelete() {
      this.$emit('on-delete', this.todo.id)
    }
  }
}
</script>

<style scoped>
  .completed {
    text-decoration: line-through;
    color: #656565;
  }
  div {
    color: #333;
    height: 15px;
    width: 250px;
    background-color: #fafafa;
    display: inline-block;
    padding: 20px 10px;
    box-shadow: 0px 0px 5px rgba(0,0,0,0.1);
    margin: 15px 0px;
    border-radius: 5px;
  }

  span {
    display: inline-block;
    vertical-align: middle;
  }
</style>