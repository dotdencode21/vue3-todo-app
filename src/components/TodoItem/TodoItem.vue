<template>
  <div class="todo-item-wrapper">
    <div class="todo-item-body">
      <div class="todo-item-info">
        <input
          v-model="todo.checked"
          type="checkbox" 
        />
        <span :class="{ 'completed': todo.checked }">{{ todo.description }}</span>
      </div>
      <div class="todo-item-btn">
        <button
          @click="handleDeleteTodo"
          type="button"
        >Delete</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  todo: {
    type: Object
  }
});

const emit = defineEmits(["deleteTodo"]);

const handleDeleteTodo = () => emit("deleteTodo", props.todo.id);
</script>

<style scoped>
  .todo-item-wrapper {
    padding-top: 24px;
    gap: 15px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .todo-item-body {
    width: 400px;
    height: auto;
    border: 1px solid #808080;
    background-color: #fff;
    border-radius: 10px;
    padding: 10px 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .todo-item-info input[type="checkbox"] {
    margin-top: 5px;
    margin-right: 10px;
    cursor: pointer;
  }

  .todo-item-info span {
    height: auto;
    padding: 3px;
    width: 250px;
    font-size: 18px;
    letter-spacing: 1px;
  }

  .completed {
    text-decoration: line-through;
  }

  .todo-item-btn button {
    width: 75px;
    height: auto;
    background-color: #dc143c;
    color: #fff;
    letter-spacing: 1px;
    font-size: 14px;
    padding: 7px 0px 7px;
    border-radius: 10px;
    cursor: pointer;
    font-weight: 600;
    border: 1px solid #808080;
  }
</style>