<template>
  <div class="todo-form-wrapper">
    <h2 class="todo-form-title">Todo App on Vue.js</h2>
    <div class="todo-form-controls">
      <input 
        type="text" 
        placeholder="Your todo is?"
      />
      <button 
        type="button"
      >Add</button>
    </div>
  </div>
</template>

<script setup>

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