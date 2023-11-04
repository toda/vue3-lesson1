<script setup>
    defineProps(['todoList']);
    const emit = defineEmits(['removeTodoChild']);
    const clickRemove = (i) =>  emit('removeTodoChild', i);
</script>

<template>
    <ul class="todo-list" v-if="todoList.length > 0">
        <li v-for="(todo, i) in todoList" v-bind:key="i">{{ todo }} <button @click="clickRemove(i)" style="cursor: pointer;">x</button></li>
    </ul>
    <p v-else>todoを追加してください。</p>
</template>

<style scoped>
    .todo-list {
        list-style: none;
    }
</style>
