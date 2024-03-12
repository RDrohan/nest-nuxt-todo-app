<template>
  <div class="container mx-auto p-12">
    <h1 class="text-3xl font-bold mb-8">Todo List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from "~/components/TodoList.vue";
import AddTodo from "~/components/AddTodo.vue";

export default {
  components: {
    TodoList,
    AddTodo,
  },
};
</script>

<style>
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>
