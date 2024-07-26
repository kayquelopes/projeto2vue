<script setup>
  defineProps(['produto']);
  defineEmits(['mostrar'])
</script>

<template>
  
        <div  class="resultado">
          <h2>Resultado</h2>
          <h3>Informações do usuario</h3>
          <p>Nome: {{ produto.nome }}</p>
          <p>E-mail {{ produto.email }}</p>
          <p>Senha: {{ produto.senha }}</p>
          <p>Confirmação de Senha: {{ produto.confirmS }}</p>
          <p>Data de Nascimento: {{ produto.dnasc }}</p>
          <p>Endereço: {{ produto.enderoco }}</p>
          <p>Estado: {{ produto.estado }}</p>
          <p>Hobbies: {{ produto.hobbie }}</p>
          <p>liguagem: {{ produto.linguagem }}</p>
          <button @click="$emit('mostrar')">editar</button>
        </div>
      
</template>

<style scoped>
h2{
  margin: 0 0 15px 0;
  padding: 0;margin: 0 0 15px 0;
  padding: 0;
  color: white;
  text-align: center;
}
h3{
  margin: 0 0 15px 0;
  padding: 0;margin: 0 0 15px 0;
  padding: 0;
  color: white;
  text-align: center;
}
.resultado{
  min-height: 80vh;
  width: 50vw;
  border-radius: 10px;
  padding: 10px;
  background-color: rgb(255, 255, 255);
  background-image: linear-gradient(to bottom right, rgb(38, 18, 109), rgb(67, 33, 190));
  color: white;
}
</style>