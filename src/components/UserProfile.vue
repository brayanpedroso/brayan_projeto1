<script setup>
import { computed } from 'vue'
import { toRefs } from 'vue'
const props = defineProps(['user'])


const estados = {
  AC: 'Acre',
  AL: 'Alagoas',
  AP: 'Amapá',
  AM: 'Amazonas',
  BA: 'Bahia',
  CE: 'Ceará',
  DF: 'Distrito Federal',
  ES: 'Espírito Santo',
  GO: 'Goiás',
  MA: 'Maranhão',
  MT: 'Mato Grosso',
  MS: 'Mato Grosso do Sul',
  MG: 'Minas Gerais',
  PA: 'Pará',
  PB: 'Paraíba',
  PR: 'Paraná',
  PE: 'Pernambuco',
  PI: 'Piauí',
  RJ: 'Rio de Janeiro',
  RN: 'Rio Grande do Norte',
  RS: 'Rio Grande do Sul',
  RO: 'Rondônia',
  RR: 'Roraima',
  SC: 'Santa Catarina',
  SP: 'São Paulo',
  SE: 'Sergipe',
  TO: 'Tocantins',
}


const { user } = toRefs(props)
const estadoName = computed(() => estados[user.value.estado])
</script>


<template>
  <div>
    <h2>Perfil do Usuário</h2>
    <p><strong>Nome:</strong> {{ user.nome }}</p>
    <p><strong>E-mail:</strong> {{ user.email }}</p>
    <p><strong>Data de Nascimento:</strong> {{ user.dataNascimento }}</p>
    <p><strong>Endereço:</strong> {{ user.endereco }}</p>
    <p><strong>Cidade:</strong> {{ user.cidade }}</p>
    <p><strong>Estado:</strong> {{ estadoName }}</p>
    <p><strong>Hobbies:</strong> {{ user.hobbies }}</p>
    <p><strong>Linguagens de Programação:</strong> {{ user.linguagens }}</p>
    <p><strong>Biografia:</strong> {{ user.biografia }}</p>
  </div>
</template>
<style scoped>
div {
  max-width: 800px;
  margin: 2rem auto;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #ffffff;
}

/* Estilo do título */
h2 {
  margin-bottom: 1rem;
  font-size: 2rem;
  color: #333;
}

/* Estilo dos parágrafos */
p {
  margin-bottom: 0.75rem;
  font-size: 1.1rem;
  color: #555;
}

strong {
  font-weight: bold;
  color: #333;
}


p:not(:last-of-type) {
  border-bottom: 1px solid #eee;
  padding-bottom: 0.5rem;
}

</style>
