<script setup>
import { useTodoListStore } from '../stores/todoList';
import { storeToRefs } from 'pinia';

const store = useTodoListStore();

const { todoList } = storeToRefs(store);

const { toggleCompleted, deleteTodo } = store;
</script>

<template>
    <div v-for="todo in todoList" :key="todo.id" class="item">
    <div class="content">
        <span :class="{ completed: todo.comleted }">{{ todo.item }}</span>
        <div>
            <span @click.stop="toggleCompleted(todo.id)">&#10004;</span>
            <span @click="deleteTodo(todo.id)" class="x">&#10060;</span>
        </div>
    </div>
    </div>
</template>

<style scoped> 
span {
    cursor: pointer;
    margin: 0 10px;
}

.item {
    display: flex;
    justify-content: center;
}

.content {
    display: flex;
    justify-content: space-between;
    width: 80vw;
    padding: 5px;
    font-size: 1.5em;

}
.completed {
    text-decoration: line-through;
} 
</style>
```