<script setup>
import { ref } from 'vue'
import { useTodoListStore } from '@/stores/todoList';

const todo = ref('');

const todoListStore = useTodoListStore();

function addItemAndClear(item) {
    if (item.length === 0) {
        return;
    }
    todoListStore.addTodo(item);
    todo.value = '';
}
</script>

<template>
    <div>
        <form @submit.prevent="addItemAndClear(todo)">
            <input v-model="todo" type="text"> <button>Add</button>
        </form>
    </div>
</template>

<style scoped>
form {
    display: flex;
    justify-content: center;
    margin-bottom: 2vh;
}
input {
    width: 50%;
    padding: 1vh;
    border: 1px solid #ccc;
    border-radius: 5px;
}
button {
    padding: 1vh;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-left: 1vw;
}

</style>
