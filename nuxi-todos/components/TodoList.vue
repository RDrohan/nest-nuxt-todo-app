<template>
  <div class="container mx-auto">
    <AddTodo v-on:submit="getTodo" />
    <ul class="divide-y divide-gray-200">
      <li v-for="todo in todos" :key="todo.id" class="py-4">
        <div class="flex items-center justify-between">
          <div class="flex items-center">
            <input
              type="checkbox"
              v-model="todo.completed"
              @change="updateTodoStatus(todo)"
              class="h-6 w-6 mr-4 text-indigo-600"
            />
            <span
              :class="{ 'line-through': todo.completed }"
              class="text-lg text-gray-800"
              >{{ todo.title }}</span
            >
          </div>
          <div>
            <button
              @click="deleteTodo(todo.id)"
              class="text-red-500 hover:underline ml-4"
            >
              Delete
            </button>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      todos: [],
    };
  },
  async mounted() {
    this.fetchTodos();
  },
  methods: {
    getTodo() {
      this.fetchTodos();
    },
    async fetchTodos() {
      try {
        const response = await axios.get("http://localhost:3000/todos");
        this.todos = response.data;
      } catch (error) {
        console.error("Error fetching todos:", error);
      }
    },
    async updateTodoStatus(todo) {
      try {
        await axios.put(`http://localhost:3000/todos/${todo.id}`, todo);
      } catch (error) {
        console.error("Error updating todo status:", error);
      }
    },
    async deleteTodo(todoId) {
      try {
        await axios.delete(`http://localhost:3000/todos/${todoId}`);
        this.todos = this.todos.filter((todo) => todo.id !== todoId);
      } catch (error) {
        console.error("Error deleting todo:", error);
      }
    },
  },
};
</script>

<style>
.line-through {
  text-decoration: line-through;
}
</style>
