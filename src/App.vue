<template>
  <div class="wrapper">
    <TodoForm/>
    <TodoItem/>
  </div>
</template>

<script setup>
import TodoForm from "./components/TodoForm/TodoForm.vue";
import TodoItem from "./components/TodoItem/TodoItem.vue";

</script>

<style scoped>
 .wrapper {
  height: 100vh;
  margin: 0 auto;
  max-width: 860px;
 }
</style>
