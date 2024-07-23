<script setup>
  import { ref } from 'vue'
import formularioBox from './formularioBox.vue';


  const showContent = ref(false);

  const buttonText = computed(() =>
    showContent.value ? 'Esconder' : 'Mostrar',
  );
</script>

<template>
  <div>
    <formulario-Box />
  </div>
  
  <button @click="showContent=!showContent">{{buttonText}}</button>
  <div v-if="showContent" class="expand-box">
    
  </div>
  
</template>

<style scoped>
  .expand-box {
    height: 100%;
    padding: 20px;
    border: 1px solid gray;
    border-radius: 5px;
    box-shadow: 3px 3px 2px 2px gray;
  }
</style>
