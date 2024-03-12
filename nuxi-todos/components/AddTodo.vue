<template>
  <div class="my-4">
    <h2 class="text-2xl font-bold mb-4">Add Todo</h2>
    <form @submit.prevent="handleSubmit">
      <input
        type="text"
        v-model="title"
        class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:border-indigo-500"
        placeholder="Enter todo title"
      />
      <button
        type="submit"
        class="mt-2 bg-indigo-500 text-white py-2 px-4 rounded-md hover:bg-indigo-600 focus:outline-none focus:bg-indigo-600"
      >
        Add Todo
      </button>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    async handleSubmit() {
      try {
        const newTodo = await axios.post("http://localhost:3000/todos", {
          title: this.title,
          completed: false,
        });
        this.title = "";
        this.$emit("submit", newTodo);
      } catch (error) {
        console.error("Error adding todo:", error);
      }
    },
  },
};
</script>
