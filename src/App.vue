<script setup>
import formulario from './components/formulario.vue';
import resultado from './components/resultado.vue'
import { reactive, ref } from 'vue';
const produto = reactive({
  nome: '',
  email: '',
  senha: '',
  confirmS: '',
  estado: [],
  hobbie: [],
  linguagem: []
});
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
const hobbies = [
  { id: 'Futebol', name: 'Futebol' },
  { id: 'Ler', name: 'Ler' },
  { id: 'Desenhar', name: 'Desenhar' },
  { id: 'Jogar Videogame', name: 'Jogar Videogame' }
];
const linguagens = [
  { id: 'JavaScript', name: 'JavaScript' },
  { id: 'python', name: 'python' },
  { id: 'c++', name: 'c++' },
  { id: 'php', name: 'php' }
];
const mostrarResultado = ref(false)

function motrarResultado(){
  mostrarResultado.value = !mostrarResultado.value
}

</script>

<template>
  
  <div class="container">
   <div>
    <formulario v-if="!mostrarResultado" @mostrar="motrarResultado" :produto="produto" :linguagens="linguagens"  :hobbies ="hobbies" :estados ="estados" />
    <resultado v-if="mostrarResultado" @mostrar="motrarResultado" :produto="produto"/>
  </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  column-gap: 2rem;
}

</style>
