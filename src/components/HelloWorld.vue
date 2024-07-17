<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <h1 class="text-yellow-900">{{ msg }} <span>Tailwind working</span></h1>
  

 
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
