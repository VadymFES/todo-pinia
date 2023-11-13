<script setup>
import TodoForm from './TodoForm.vue'
import TodoList from './TodoList.vue'
</script>

<template>
    <div class="todo-app">
        <h1>To do list</h1>
        <todo-form  />
        <todo-list /> 
    </div>
</template>

<style scoped>  
    .todo-app {
    padding: 5vh;
    min-height: 100vh;
    background-color: #f7f9fc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    }

    h1 {
    text-align: center;
    margin-bottom: 2vh;
    }
</style>
```