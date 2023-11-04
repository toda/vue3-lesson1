<script setup>
import { computed, ref } from 'vue';
const url = 'https://yahoo.co.jp';
const flag = false;
const name = ref('test');
const array = [
        {
            name: '久保',
            height: 173,
        },
        {
            name: '富安',
            height: 187,
        },
        {
            name: '三苫',
            height: 178,
        },
    ];
const filterHeight = 180;
const filterArrayByHeight = computed(() => {
    return array.filter(c => c.height >= filterHeight);
});
const testMethod = (str, e) => {
    console.log(str);
    console.log(e);
};
</script>

<template>
    <a v-bind:href="url" target="_blank">移動する</a>
    <form>
        <label for="hoge">サンプル</label>
        <input type="text" id="hoge" v-model.trim="name" />
        <p>{{ name }}</p>
        <input type="button" class="type" :disabled="flag" value="button" @click="testMethod('sample', $event)" />
    </form>
    <div v-for="(item, i) in array" v-bind:key="i">
        <p>{{ item.name }} : {{ item.height }}</p>
    </div>

    <p>filter lather than height {{ filterHeight }}.</p>
    <div v-for="(item, i) in filterArrayByHeight" v-bind:key="i">
        <p>{{ item.name }} : {{ item.height }}</p>
    </div>
</template>
