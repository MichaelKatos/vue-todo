<template>
  <header class="header">
    <h1>Todo List</h1>
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
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
  padding-right: 0.7rem;
  text-decoration: none;
  padding-left: 0.7rem;
}
</style>
