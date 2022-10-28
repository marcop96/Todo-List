<script setup lang="ts">
import { ref } from "vue";
import { NInput, NButton } from "naive-ui";
let id = 0;
const newTodo = ref("");
const todos = ref([
  {
    id: id++,
    text: "placeholder",
  },
]);

function addTask() {
  console.log(newTodo.value);
  todos.value.push({ id: id++, text: newTodo.value });
}
</script>

<template>
  <div class="flex place-content-center mt-6">
    <div class="flex w-72">
      <NInput v-model:value="newTodo" placeholder="Write your task here">
      </NInput>
      <n-button size="small" @click="addTask">Add task </n-button>
    </div>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
      </li>
    </ul>
  </div>
</template>
