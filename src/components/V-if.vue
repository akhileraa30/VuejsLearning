<template >
    <div>
        <p class="p-1 bg-slate-200 w-1/4">{{msg}}</p>
        <button @click="good=!good" >toggle</button>
        <p v-if="good">i am good</p>
        <p v-else>i am not good</p>
    </div>
</template>
<script setup>
defineProps({
    msg:String
})
import { ref } from 'vue';

const good = ref(false);
</script>
<style >
    
</style>