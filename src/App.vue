<script setup>
import { computed, ref } from 'vue'

const contador = ref(0)

const boleano = ref(true)

function incrementar(variavel) {
  eval(variavel).value++
}
function decrementar(variavel) {
  eval(variavel).value--
}
</script>

<template>
  <button @click="boleano = !boleano">colorido</button>

  <div v-if="boleano">
    <label for="v-model">Escolher cor: </label>
    <select v-model="selectedColor">
      <option value="red">Vermelho</option>
      <option value="green">Verde</option>
      <option value="blue">Azul</option>
      <option value="gray">Cor padrão</option>
    </select>

    <div>
      <button @click="incrementar('contador')">incrementar +</button>
      <button @click="decrementar('contador')">decrementar -</button>

      <p :style="{ backgroundColor: selectedColor }" class="color">{{ contador }}</p>
    </div>
  </div>
  <div v-else class="cor">
    <label for="v-model">Escolher cor: </label>
    <select v-model="selectedColor">
      <option value="red">Vermelho</option>
      <option value="green">Verde</option>
      <option value="blue">Azul</option>
      <option value="gray">Cor padrão</option>
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
select {
  background-color: black;
  color: white;
}
option {
  background-color: black;
  color: white;
}
p {
  color: black;
}

  @keyframes pererecasuicida {
    from {
      color: red;
    }
    0% {
      color: orange;
    }
    20% {
      color: yellow;
    }
    40% {
      color: greenyellow;
    }
    60% {
      color: green;
    }
    80% {
      color: blue;
    }
    90% {
      color: purple;
    }
    to {
      color: red;
    }
  }

  .cor{
    animation: pererecasuicida 5s infinite;
  }
  .cor p{
    animation: pererecasuicida 5s infinite;
  }
  .cor button{
    animation: pererecasuicida 5s infinite;
  }
  p{
    background-color: gray;
  }
</style>
