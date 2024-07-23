<script setup>
import { ref } from 'vue'
import ExpandBox from './components/expandBox.vue'
import formularioBox from './components/formularioBox.vue';



const email = ref('')
const nome = ref('')
const dataN = ref('')
const endereço = ref('')
const cidade = ref('')
const estado = ref('')
const Hobbies = ref('')
const Linguagens = ref('')
const Biografia = ref('')
const senha = ref('')
const confirmaçao = ref('')
const botaoDados = ref(false)
</script>

<template>
 <div>
 <formularioBox/>
 </div>
   <div>
    <expand-box />
  </div>

  <expand-box title="Título da caixa de expansão 1" />
    
   
</template>

<style scoped>
.titulo {
  margin: 1rem 2rem;
  border-radius: 20px;
  padding: 0.75rem;
  display: flex;
  gap: 1rem;
}
.formulario,
.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px;
}
.formulario {
  background-color: #d29696;
}
.formulario .row {
  width: 80%;
  margin: 1.3rem 0;
  display: flex;
  justify-content: space-between;
}
.resultado {
  background-color: #98e0aa;
}

button {
  padding: 0.5rem 1rem;
  border: none;
  background-color: #f1f1f1;
  border-radius: 10px;
  cursor: pointer;
}
button:hover {
  background-color: #e1e1e1;
}
</style>
