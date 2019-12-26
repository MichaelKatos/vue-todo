<template>
  <div>
    <form>
      <input type="text" name="title" placeholder="Add Todo..." />
      <input type="submit" value="+" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo"
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

.btn {
  border: none;
  background: green;
  color: #fff;
  font-size: 3rem;
}
</style>