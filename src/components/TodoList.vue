<script setup lang="ts">
import { ref } from "vue";
import { NInput, NButton } from "naive-ui";
const task = ref("");
</script>

<template>
  <div class="flex place-content-center mt-6">
    <div class="flex w-72">
      <NInput v-model:value="task" placeholder="Write your task here"> </NInput>
      <n-button size="small">Add task </n-button>
    </div>
  </div>
  <h1>{{ task }}dsa</h1>
</template>
