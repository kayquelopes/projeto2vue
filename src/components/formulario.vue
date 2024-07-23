<script setup>
  import { ref,defineProps } from 'vue';
  defineProps(['produto', 'linguagens', 'hobbies', 'estados']);
  const mostrarResultado = ref(false);
</script>

<template>
  <form @submit.prevent="" v-if="!mostrarResultado">
    <h1>Formulario</h1>
    <div class="row">
      <label for="nome">Nome: </label>
      <input type="text" v-model="produto.nome" minlength="3" maxlength="50" />
    </div>
    <div class="row">
      <label for="email">Email: </label>
      <input type="email" v-model="produto.email" />
    </div>
    <div class="row">
      <label for="senha">Senha: </label>
      <input type="password" name="senha" v-model="produto.senha" />
      <label for="confirmS">Confirmação de senha: </label>
      <input type="password" name="confirmS" v-model="produto.confirmS" />
    </div>
    <div class="row">
      <label for="dnasc">Data de Nascimento: </label>
      <input type="date" v-model="produto.dnasc" />
    </div>
    <div class="row">
      <label for="enderoco">Endereço: </label>
      <input type="text" v-model="produto.enderoco" />
    </div>
    <fieldset>
      <legend>Estados</legend>
      <div class="itens-estados">
        <div v-for="estado in estados" :key="estado.id">
          <input type="checkbox" v-model="produto.estado" :value="estado.id" />{{ estado.name }}
        </div>
      </div>
    </fieldset>
    <fieldset>
      <legend>Hobbies</legend>
      <div class="itens-estados">
        <div v-for="hobbie in hobbies" :key="hobbie.id">
          <input type="checkbox" v-model="produto.hobbie" :value="hobbie.id" />{{ hobbie.name }}
        </div>
      </div>
    </fieldset>
    <fieldset>
      <legend>Linguagens</legend>
      <div class="itens-estados">
        <div v-for="linguagem in linguagens" :key="linguagem.id">
          <input type="checkbox" v-model="produto.linguagem" :value="linguagem.id" />{{
            linguagem.name
          }}
        </div>
      </div>
    </fieldset>
    <button @click="$emit('mostrar')">Enviar</button>
  </form>
  
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
  padding: 0;margin: 0 0 15px 0;
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

