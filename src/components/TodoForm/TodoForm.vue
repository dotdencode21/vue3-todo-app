<template>
  <div class="todo-form-wrapper">
    <h2 class="todo-form-title">Todo App on Vue.js</h2>
    <div class="todo-form-controls">
      <input 
        v-model="currentTodo"
        type="text" 
        placeholder="E.g. buy milk"
      />
      <button 
        type="button"
        @click="addTodo"
      >Add</button>
    </div>
  </div>
  <div v-for="todo in todos">
      <TodoItem 
        :key="todo.id"
        :todo="todo"
        @deleteTodo="deleteTodo"
      />
    </div>
</template>

<script setup>
import { ref } from "vue";
import TodoItem from "../TodoItem/TodoItem.vue";

const currentTodo = ref("");
const todos = ref([]);

const addTodo = () => {
  const newTodo = {
    id: Math.random() * 1000,
    checked: false,
    description: currentTodo.value || "Text"
  }

  todos.value.push(newTodo);
  currentTodo.value = "";
}

const deleteTodo = todoId => {
  todos.value = todos.value.filter(todo => todo.id !== todoId);
}
</script>

<style scoped>
  .todo-form-wrapper {
    border-bottom: 1px solid #808080;
    text-align: center;
  }

  .todo-form-title {
    letter-spacing: 1px;
    padding: 15px;
  }

  .todo-form-controls {
    padding: 25px;
  }

  .todo-form-controls input {
    width: 300px;
    height: auto;
    padding: 5px;
    font-size: 18px;
  }

  .todo-form-controls button {
    margin-left: 10px;
    height: auto;
    width: 75px;
    font-size: 18px;
    background-color: #228B22;
    color: #fff;
    font-weight: 600;
    letter-spacing: 1px;
    padding: 7px 0px 7px;
    border-radius: 10px;
    cursor: pointer;
    border: 1px solid #808080;
  }
</style>