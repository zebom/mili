<script setup>
import { ref } from 'vue';

const count = ref (0)

function increment(){
  count.value++
}

function decrement(){
  count.value--
}
</script>

<template>
  <h1>welcome home</h1>
  <h1> Counter App</h1>
<!-- <button v-on:click="count++">Increment</button> -->
<button @click="increment">Increment</button>
<button @click="decrement">decrement</button>


<p>{{count}}</p>

</template>
<style scoped>
button{
  border-radius: 10px
}
</style>
