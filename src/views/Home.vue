<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id) {
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(res => {
          window.console.log(res);
          this.todos = this.todos.filter(todo => todo.id !== id);
        })
        .catch(err => window.console.log(err));
    },
    addTodo(newTodo) {
      const { title, completed } = newTodo;
      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title,
          completed
        })
        .then(res => (this.todos = [...this.todos, res.data]))
        .catch(err => window.console.log(err));
    }
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=8")
      .then(res => (this.todos = res.data))
      .catch(err => window.console.log(err));
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

.btn {
  display: inline-block;
  padding: 0.7rem 2rem;
  cursor: pointer;
  background: #229922;
  color: #fff;
  font-size: 3rem;
  outline: none;
  border: none;
  box-shadow: 2px 1px 2px rgba(0, 0, 0, 0.2);
}

.btn:hover {
  background: #228822;
  font-size: 3.3rem;
}
</style>
