<script setup>
import { reactive } from 'vue'

const produto = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmS: '',
  estado: [],
  hobbie: [],
  linguagem: [],
})
const estados = [
  { id: 'AC', name: 'Acre' },
  { id: 'AL', name: 'Alagoas' },
  { id: 'AP', name: 'Amapá' },
  { id: 'AM', name: 'Amazonas' },
  { id: 'BA', name: 'Bahia' },
  { id: 'CE', name: 'Ceará' },
  { id: 'DF', name: 'Distrito Federal' },
  { id: 'ES', name: 'Espírito Santo' },
  { id: 'GO', name: 'Goiás' },
  { id: 'MA', name: 'Maranhão' },
  { id: 'MT', name: 'Mato Grosso' },
  { id: 'MS', name: 'Mato Grosso do Sul' },
  { id: 'MG', name: 'Minas Gerais' },
  { id: 'PA', name: 'Pará' },
  { id: 'PB', name: 'Paraíba' },
  { id: 'PR', name: 'Paraná' },
  { id: 'PE', name: 'Pernambuco' },
  { id: 'PI', name: 'Piauí' },
  { id: 'RJ', name: 'Rio de Janeiro' },
  { id: 'RN', name: 'Rio Grande do Norte' },
  { id: 'RS', name: 'Rio Grande do Sul' },
  { id: 'RO', name: 'Rondônia' },
  { id: 'RR', name: 'Roraima' },
  { id: 'SC', name: 'Santa Catarina' },
  { id: 'SP', name: 'São Paulo' },
  { id: 'SE', name: 'Sergipe' },
  { id: 'TO', name: 'Tocantins' }
];
const hobbies = [{ id: 'Futebol', name: 'Futebol' },
{ id: 'Ler', name: 'Ler' },
{ id: 'Desenhar', name: 'Desenhar' },
{ id: 'Jogar Videogame', name: 'Jogar Videogame' },];
const linguagens = [{ id: 'JavaScript', name: 'JavaScript' },
{ id: 'python', name: 'python' }, { id: 'c++', name: 'c++' }, { id: 'php', name: 'php' },
]
</script>

<template>
  <div class="container">
    <form @submit.prevent="">
      <h1>Formulario</h1>
      <div class="row">
        <label for="nome">Nome: </label>
        <input type="text" v-model="produto.nome" minlength="3" maxlength="50">
      </div>
      <div class="row">
        <label for="email">Email: </label>
        <input type="email" v-model="produto.email">
      </div>
      <div class="row">
        <label for="senha">Senha: </label>
        <input type="password" name="senha" v-model="produto.senha">
        <label for="confirmS">Confirmação de senha: </label>
        <input type="password" name="confirmS" v-model="produto.confirmS">
      </div>
      <div class="row">
        <label for="dnasc">Data de Nascimento: </label>
        <input type="date" v-model="produto.dnasc">
      </div>
      <div class="row">
        <label for="enderoco">Endereço: </label>
        <input type="text" v-model="produto.enderoco">
      </div>
      <fieldset>
        <legend>Estados</legend>
        <div class="itens-estados">
          <div v-for="estado in estados" :key="estado.id">
            <input type="checkbox" v-model="produto.estado" :value=estado.id>{{ estado.name }}
          </div>
        </div>
      </fieldset>
      <fieldset>
        <legend>Hobbies</legend>
        <div class="itens-estados">
          <div v-for="hobbie in hobbies" :key="hobbie.id">
            <input type="checkbox" v-model="produto.hobbie" :value=hobbie.id>{{ hobbie.name }}
          </div>
        </div>
      </fieldset>
      <fieldset>
        <legend>Linguagens</legend>
        <div class="itens-estados">
          <div v-for="linguagem in linguagens" :key="linguagem.id">
            <input type="checkbox" v-model="produto.linguagem" :value=linguagem.id>{{ linguagem.name }}
          </div>
        </div>
      </fieldset>
      <button>Enviar</button>
    </form>
  </div>
</template>

<style scoped>
button {
  background-color: rgb(182, 182, 182);
  color: black;
  margin: 0.5cm 0 0 0;
  height: 40px;
  width: 60px;
  border: 1px solid black;
  border-radius: 10px;
}

.container {
  display: flex;
  align-items: center;
  justify-content: center;
  column-gap: 2rem;
}

.itens-estados {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

form {
  min-height: 80vh;
  width: 50vw;
  border-radius: 10px;
  padding: 10px;
  background-color: rgb(255, 255, 255);
  background-image: linear-gradient(to bottom right, rgb(38, 18, 109), rgb(67, 33, 190));
}

h1 {
  margin: 0 0 15px 0;
  padding: 0;
  color: white;
  text-align: center;
}

fieldset {
  color: white;
}

.row {
  margin-bottom: 4px;
}
</style>