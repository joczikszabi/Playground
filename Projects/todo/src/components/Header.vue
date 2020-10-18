<template>
  <header>
    {{ title }}
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    title: String
  }
}
</script>

<style scoped>
  header {
    height: 50px;
    line-height: 50px;
    color: #fafafa;
    background-color: #222;
    text-align: center;
  }
</style>