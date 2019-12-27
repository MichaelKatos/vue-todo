<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add Todo..."
      />
      <input type="submit" value="+" class="btn" />
    </form>
  </div>
</template>

<script>
//import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (!this.title) {
        return;
      }
      const newTodo = {
        title: this.title,
        completed: false
      };
      //Send up to parent
      this.$emit("add-todo", newTodo);

      this.title = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 0.8rem;
  line-height: 2.2rem;
  border: none;
  box-shadow: 2px 1px 2px rgba(0, 0, 0, 0.2);
  font-size: 1.5rem;
}

input[type="submit"] {
  flex: 1;
  padding: 0.8rem;
  line-height: 2rem;
  box-shadow: 2px 1px 2px rgba(0, 0, 0, 0.2);
}
</style>
