<script setup>
    defineProps(['color']);
</script>

<template>
    <header>
        <h1 :style="{'color': color}"><slot>TODO</slot></h1>
    </header>
</template>
