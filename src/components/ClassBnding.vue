<template>
    <div>
        <p class="p-1 bg-slate-200 w-1/4">{{msg}}</p>
        
        <p :class="isActive ? 'red' : 'green'" @click="handleclick" class="font-bold">My Name: {{ name }}</p>
    </div>
</template>
<script setup>
    import { ref } from 'vue'

    const name = "Ramesh"
    const isActive=ref(false)

    const handleclick=()=>{
        isActive.value=!isActive.value
    }
 defineProps({
    msg:String
 })
</script>
<style>
.red{
    color:red
}
.green{
    color:green
}
</style>