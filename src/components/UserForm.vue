<script setup>
import { ref } from 'vue';
const emit = defineEmits(['update-user']);

const formData = ref({
  nome: '',
  email: '',
  senha: '',
  confirmaSenha: '',
  dataNascimento: '',
  endereco: '',
  cidade: '',
  estado: '',
  hobbies: '',
  linguagens: '',
  biografia: '',
});

const estados = [
  { value: 'AC', name: 'Acre' },
  { value: 'AL', name: 'Alagoas' },
  { value: 'AP', name: 'Amapá' },
  { value: 'AM', name: 'Amazonas' },
  { value: 'BA', name: 'Bahia' },
  { value: 'CE', name: 'Ceará' },
  { value: 'DF', name: 'Distrito Federal' },
  { value: 'ES', name: 'Espírito Santo' },
  { value: 'GO', name: 'Goiás' },
  { value: 'MA', name: 'Maranhão' },
  { value: 'MT', name: 'Mato Grosso' },
  { value: 'MS', name: 'Mato Grosso do Sul' },
  { value: 'MG', name: 'Minas Gerais' },
  { value: 'PA', name: 'Pará' },
  { value: 'PB', name: 'Paraíba' },
  { value: 'PR', name: 'Paraná' },
  { value: 'PE', name: 'Pernambuco' },
  { value: 'PI', name: 'Piauí' },
  { value: 'RJ', name: 'Rio de Janeiro' },
  { value: 'RN', name: 'Rio Grande do Norte' },
  { value: 'RS', name: 'Rio Grande do Sul' },
  { value: 'RO', name: 'Rondônia' },
  { value: 'RR', name: 'Roraima' },
  { value: 'SC', name: 'Santa Catarina' },
  { value: 'SP', name: 'São Paulo' },
  { value: 'SE', name: 'Sergipe' },
  { value: 'TO', name: 'Tocantins' },
];

function submitForm() {
  if (formData.value.senha !== formData.value.confirmaSenha) {
    alert('As senhas não coincidem!');
    return;
  }

  const userData = { ...formData.value };
  delete userData.confirmaSenha;

  emit('update-user', userData);
}
</script>


<template>
  <form @submit.prevent="submitForm">
    <div>
      <label for="nome">Nome:</label>
      <input id="nome" v-model="formData.nome" required />
    </div>
    <div>
      <label for="email">E-mail:</label>
      <input id="email" v-model="formData.email" type="email" required />
    </div>
    <div>
      <label for="senha">Senha:</label>
      <input id="senha" v-model="formData.senha" type="password" required />
    </div>
    <div>
      <label for="confirmaSenha">Confirmação de Senha:</label>
      <input id="confirmaSenha" v-model="formData.confirmaSenha" type="password" required />
    </div>
    <div>
      <label for="dataNascimento">Data de Nascimento:</label>
      <input id="dataNascimento" v-model="formData.dataNascimento" type="date" required />
    </div>
    <div>
      <label for="endereco">Endereço:</label>
      <input id="endereco" v-model="formData.endereco" required />
    </div>
    <div>
      <label for="cidade">Cidade:</label>
      <input id="cidade" v-model="formData.cidade" required />
    </div>
    <div>
      <label for="estado">Estado:</label>
      <select id="estado" v-model="formData.estado" required>
        <option v-for="estado in estados" :key="estado.value" :value="estado.value">
          {{ estado.name }}
        </option>
      </select>
    </div>
    <div>
      <label for="hobbies">Hobbies:</label>
      <textarea id="hobbies" v-model="formData.hobbies"></textarea>
    </div>
    <div>
      <label for="linguagens">Linguagens de Programação:</label>
      <textarea id="linguagens" v-model="formData.linguagens"></textarea>
    </div>
    <div>
      <label for="biografia">Biografia:</label>
      <textarea id="biografia" v-model="formData.biografia"></textarea>
    </div>
    <button type="submit">Salvar</button>
  </form>
</template>


<style scoped>
form {
  display: flex;
  flex-direction: column;
  max-width: 600px;
  margin: 0 auto;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #f9f9f9;
}

form div {
  margin-bottom: 1.5rem;
}

form label {
  display: block;
  font-weight: bold;
  margin-bottom: 0.5rem;
  color: #333;
}

form input,
form select,
form textarea {
  width: 100%;
  padding: 0.75rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

form input:focus,
form select:focus,
form textarea:focus {
  border-color: #007bff;
  outline: none;
}


button {
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 5px;
  background-color: #007bff;
  color: white;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
  margin-top: 1rem;
}

button:hover {
  background-color: #0056b3;
}

textarea {
  resize: vertical;
  min-height: 100px;
}

</style>
