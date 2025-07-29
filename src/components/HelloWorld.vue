<script setup>
import { reactive } from "vue";

let initialState = reactive({ count: 0 });
</script>

<template>
  <h1>Count : {{ initialState.count }}</h1>
  <button @click="initialState.count++">Increment</button>

  <button @click="initialState.count--">Decrement</button>
</template>
<style></style>
