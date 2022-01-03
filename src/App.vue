<template>
  <div class="container">
    <h1>My Fantastic Evergrowing Todo List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
export default {
  name: "App",
  components: {
    TodoList,
  },
};
</script>

<style>
</style>
