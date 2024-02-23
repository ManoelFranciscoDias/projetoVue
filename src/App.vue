<script setup>
import { ref } from 'vue'
const contador = ref(0)

function apagar() {
  contador.value = 0
}

function decrementar() {
  
  if (contador.value < 1) {
  alert(`O valor não pode ser menor que 0`)
}
else {
  contador.value--
}
}



</script>

<template>
  <button @click="contador++">+</button>
  <button @click="decrementar">-</button>
  <button @click="apagar"></button>
  <p>Valor do contador: {{ contador }}</p>
</template>

<style scoped>
button {
  font-weight: bold;
  background-color: rgb(31, 92, 92);
  border: 0;
  border-radius: 10px;
  color: rgb(255, 255, 255);
  margin-left: 10px;
}
</style>
