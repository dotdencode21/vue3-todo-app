<template>
  <div class="wrapper">
    <TodoForm/>
  </div>
</template>

<script setup>
import TodoForm from "./components/TodoForm/TodoForm.vue";
</script>

<style scoped>
 .wrapper {
  height: 100vh;
  margin: 0 auto;
  max-width: 860px;
 }
</style>
