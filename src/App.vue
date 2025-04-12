<script setup>

import { computed, ref } from "vue";


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
];

function incrementar(variavel) {

  eval(variavel).value++
}
function decrementar(variavel){
  eval(variavel).value--
}
function incrementarComParametros(variavel) {

    if(eval(variavel).value <= 3){

      eval(variavel).value++
    }
    else{
      eval(variavel).value = 0
    }
}
 function decrementarComParemetros(variavel) {

  if(eval(variavel).value > 0){

eval(variavel).value--
}

  else{
  eval(variavel).value = 0
  }
 }
</script>

<template>
  <div>


  <button @click="incrementar('contador')">incrementar</button>

<p :style="{ backgroundColor: contador2 == 1 ? 'green' : contador2 == 2 ? 'orange' : contador2 == 3 ? 'pink' : contador2 == 4 ? 'yellow' : 'black' }">{{ contador }}</p>

  </div>
  <button @click="incrementarComParametros('contador2')">mudar cor +</button>
  <button @click="decrementarComParemetros('contador2')">mudar cor -</button>
  <p>{{ contador2 }}</p>

</template>

<style scoped>


</style>
