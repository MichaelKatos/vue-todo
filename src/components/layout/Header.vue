<template>
  <header class="header">
    <h1>Todo List</h1>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 1rem;
  line-height: 3rem;
}

.header h1 {
  font-size: 2rem;
}
.header a {
  color: #ffffff;
  padding-right: 0.5rem;
}
</style>