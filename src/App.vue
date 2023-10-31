<!-- <script setup>
import { computed, ref } from 'vue';

const welcomeColor = "blue";
const message = computed(() => {
    return `ようこそ、<strong>${name.value}</strong>さん`;
});
const name = ref('');
</script>

<template>
    <h1>hello Vue3</h1>
    <p>お名前は？: <input type="text" size="30" v-model="name"></p>
    <p v-html="message" :style="{ color: welcomeColor}"></p>
</template> -->

<script setup>
import AppHeader from './components/AppHeader.vue';
import TodoList from './components/TodoList.vue';
import { ref } from 'vue';
const todo = ref('');
const todoList = ref([]);

const addTodo = () => {
    if (todo.value.length > 0) {
        todoList.value.push(todo.value);
        todo.value = '';
    }
};

const removeTodo = (target) => {
    todoList.value.splice(target, 1);
};
</script>

<template>
    <AppHeader color="#cde"></AppHeader>
    <input type="text" size="30" v-model="todo">
    <button @click="addTodo()">追加</button>
    <TodoList :todoList="todoList" @removeTodoChild="removeTodo"></TodoList>
</template>
