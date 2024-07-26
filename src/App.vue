
<script setup>
import { reactive, ref } from 'vue';
import UserForm from './components/UserForm.vue';
import UserProfile from './components/UserProfile.vue';


const user = reactive({
  nome: '',
  email: '',
  senha: '',
  dataNascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagens: '',
  biografia: '',
});


const showForm = ref(true);


const toggleView = () => {
  showForm.value = !showForm.value;
};

const updateUser = (newUserData) => {
  Object.assign(user, newUserData);
};
</script>

<template>
  <div>
    <button @click="toggleView">{{ showForm ? 'Mostrar Perfil' : 'Mostrar Formulário' }}</button>
    <UserForm v-if="showForm" @update-user="updateUser" />
    <UserProfile v-else :user="user" />
  </div>
</template>
<style scoped>

</style>
