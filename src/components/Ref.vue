<script>
import { ref } from "vue";

let userName = ref("");
</script>
<template>
  <h1>UserName : {{ userName }}</h1>
  <button @click="userName.value = 'vikas dagur'">Add User</button>
</template>
 
<style>

</style>