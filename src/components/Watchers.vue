<template>
    <p class="p-1 bg-slate-200 w-1/4">{{ msg }}</p>
    <div class="flex gap-2">

        <button class="px-2 border border-zinc-900" @click="count++">+</button>
        <p>{{ count }}</p>
        <button class="px-2 border border-zinc-900" @click="count--">-</button>
        <label for="">Ask a Yes/No Question</label>
        <input v-model="question" placeholder="Ask Your Question " :disabled="loading">
        <p>{{ answer }}</p>
        <div style="width: 100px;" >
        <img :src="path" alt="no image">
        </div>
    </div>
</template>
<script setup>
import { ref, watch } from 'vue'
const count = ref(0)
const question = ref("")
const answer = ref("Please add ? mark ")
const loading = (false)
const path=ref("")
defineProps({
    msg: String
})
watch(count, (newVal, oldVal) => {
    console.log(newVal);
    if (newVal > 5) {
        alert("Counting above 5!");
    }
});
watch(question, async(val, oldVal) => {
    if (val.includes('?')) {
       
        answer.value='thinking...'
    }
    try {
        const res = await fetch('https://yesno.wtf/api')
        answer.value=(await res.json()).answer
        
    } catch (error) {
        answer.value = 'Error! Could not reach the API. ' + error
    }
});
</script>
<style></style>