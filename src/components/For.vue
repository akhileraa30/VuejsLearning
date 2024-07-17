<template>
    <div>
        <p class="p-1 bg-slate-200 w-1/4">{{ msg }}</p>
        <li v-for="(item, index) in items">
            {{ index }} - {{ item.message }}
        </li>
        <br>
        <p v-for="(value, key) in myObject">{{value}}</p>
<div>
    <p>{{count}}</p>
    <button @click="changeCount">click</button>

</div>
    </div>
</template>
<script setup>
import { ref,onMounted } from 'vue'
const items = ref([{ message: "Hello" }, { message: "good" }, { message: "okay" }])
const myObject = ref({
    title: 'How to do lists in Vue',
    author: 'Jane Doe',
    publishedAt: '2016-04-10'
})
defineProps({
    msg: String
})
const count=ref(4)
const changeCount=()=>{
    count.value++
}

onMounted(() => {
    changeCount()
})

</script>
<style>

</style>