<template>
    <div>
        <p class="p-1 bg-slate-200 w-1/4">{{ msg }}</p>
        <div>
            <button @click="showMessage('Hello from Button 1')">Button 1</button>
            <button @click="showMessage('Hello from Button 2')">Button 2</button>
            <p v-if="message">{{ message }}</p>
        </div>
        <div>
            <p @mouseover="handleMouseOver" @mouseout="handleMouseOut" :class="{ hovered: isHovered }">
                Hover over this text to change its color.
            </p>
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue'
const message = ref('');
const isHovered = ref(false);
const showMessage = (msg) => {
    message.value = msg;
};
const handleMouseOver = () => {
  isHovered.value = true;
};
const handleMouseOut = () => {
  isHovered.value = false;
};
defineProps({
    msg: String
})
</script>
<style>
.hovered {
  color: blue;
}
</style>