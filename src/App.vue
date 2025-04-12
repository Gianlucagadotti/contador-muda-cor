<script setup>
import { computed, ref } from 'vue'

const contador = ref(0)

const contador2 = ref(0)

const muda = ref(0)

const mudarcor = [
  {
    id: 1,
    cor: 'vermelho',
  },
  {
    id: 2,
    cor: 'branco',
  },
]

function incrementar(variavel) {
  eval(variavel).value++
}
function decrementar(variavel) {
  eval(variavel).value--
}
</script>

<template>
  <div class="app">
    <label for="v-model">Escolher cor: </label>
    <select v-model="selectedColor">
      <option value="red">Vermelho</option>
      <option value="green">Verde</option>
      <option value="blue">Azul</option>
    </select>

<div>
    <button @click="incrementar('contador')">incrementar +</button>
    <button @click="decrementar('contador')">decrementar -</button>

    <p :style="{ backgroundColor: selectedColor }" class="color">{{ contador }}</p>
</div>
  </div>
</template>

<style scoped>
button {
  background-color: black;
  color: white;

}
select{
  background-color: black;
  color: white;

}
 option{
  background-color: black;
  color: white;
 }
 p{
  color: black;
 }
</style>
