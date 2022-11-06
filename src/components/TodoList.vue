<script setup lang="ts">
import { ref } from "vue";
import { NInput, NButton } from "naive-ui";
let id = 0;
const newTodo = ref("");
const todos = ref([
  {
    id: id++,
    text: "placeholder",
    completed: false,
  },
]);

function toggleComplete(task) {
  task.completed = !task.completed;
  console.log(task.completed);
}

function addTask() {
  console.log(newTodo.value);
  todos.value.push({ id: id++, text: newTodo.value, completed: false });
}
</script>

<template>
  <div class="flex place-content-center mt-6">
    <div class="flex w-72">
      <NInput v-model:value="newTodo" placeholder="Write your task here">
      </NInput>
      <n-button size="small" @click="addTask">Add task </n-button>
    </div>
  </div>

  <div class="flex place-content-center">
    <ul>
      <li v-for="todo in todos" :key="todo.id" @click="toggleComplete(todo)">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>
