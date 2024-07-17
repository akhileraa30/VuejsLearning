<script setup>
import HelloWorld from './components/HelloWorld.vue'
import ComputedProperty from './components/ComputedProperty.vue'
import ClassBinding from './components/ClassBnding.vue'
import Vif from './components/V-if.vue'
import For from './components/For.vue'
import Event from './components/Event.vue'
import Watchers from './components/Watchers.vue'
</script>

<template>
 
  <HelloWorld msg="Sending props" />
  <ComputedProperty msg="ComputedProperty"/>
  <ClassBinding msg="ClassBinding"/>
 <Vif msg="V-if"/>
 <For msg="V-For"/>
 <Event msg="Event"/>
 <Watchers msg="Watchers"/>
</template>

<style scoped>

</style>
