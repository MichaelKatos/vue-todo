<template>
  <div id="app">
    <Header />
    <AddTodo />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "app",
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Create Vue App",
          completed: true
        },
        {
          id: 2,
          title: "Run Vue App",
          completed: true
        },
        {
          id: 3,
          title: "Deploy Vue App",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-size: 10px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4rem;
}
</style>
