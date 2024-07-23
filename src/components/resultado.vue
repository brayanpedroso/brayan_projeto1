<script setup>
 import { ref } from 'vue'
import ExpandBox from './components/expandBox.vue';
</script>

<template>
<div>
    <h5>dados usuario</h5>
    <p>email digitado: {{ email }}</p>
    <p>nome digitado:{{ nome }}</p>
    <p>data de nascimento digitado:{{ dataN }}</p>
    <p>endereço digitado:{{ endereço }}</p>
    <p>cidade digitado:{{ cidade }}</p>
    <p>estado digitado:{{ estado }}</p>
    <p>Hobbies digitado:{{ Hobbies }}</p>
    <p>Linguagens digitado:{{ Linguagens }}</p>
    <p>biografia digitado:{{ Biografia }}</p>
    <p>senha digitado:{{ senha }}</p>
    <p>confirmaçao digitado:{{ confirmaçao }}</p>
  </div>
  
</template>

<style scoped>
 
</style>