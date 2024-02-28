<script setup>
//CONTADOR

import { ref } from 'vue'
const contador = ref(0)

function apagar() {
  contador.value = 0
}

function decrementar() {
  if (contador.value < 1) {
    alert(`O valor não pode ser menor que 0`)
  } else {
    contador.value--
  }
}

//INFORMAÇÕES

const nome = 'Manoel - Nicolas'
const idade = 16

function inverter(texto) {
  return texto.split('').reverse().join('')
}

function saudacao() {
  return `Olá, ${nome}!`
}
</script>

<template>
  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p>Nome: {{ nome }}</p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido é: {{ inverter(nome.toUpperCase()) }}</p>
    <hr />
    <p>Exemplo de saudação usando função</p>
    <p>{{ saudacao() }}</p>
  </div>

  <div class="contador">
    <h1 style="text-align: center">CONTADOR</h1>
    <p style="color: white; text-align: center">VALOR: {{ contador }}</p>
    <button @click="contador++">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <button @click="apagar">Reiniciar</button>

    <div v-if="contador < 10" style="background-color: red; margin-top: 10px; color: black">
      O número é menor que 10.
    </div>
    <div v-if="contador > 10" style="background-color: green; margin-top: 10px; color: black">
      O número é maior que 10.
    </div>
    <div
      v-if="contador == 10"
      style="background-color: rgb(166, 255, 1); margin-top: 10px; color: black"
    >O número é 10.
    </div>
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
  background-color: rgb(31, 92, 92);
  border: 0;
  border-radius: 10px;
  color: rgb(255, 255, 255);
  margin-left: 10px;
  margin-top: 15px;
  margin-left: 20px;
}

button:hover {
  background-color: rgb(44, 153, 153);
}

.info {
  background-color: rgb(0, 0, 0);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

.contador {
  background-color: rgb(28, 63, 63);
  border-radius: 10px;
  margin-left: 10px;
}
</style>
