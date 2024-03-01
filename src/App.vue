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

const nome = prompt(`Informe o seu nome`)
const idade = Number(prompt(`Informe a sua idade`))

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

    <div class="msgRed" v-if="contador < 10">O número é menor que 10.</div>

    <div class="msgGreen" v-if="contador > 10">O número é maior que 10.</div>

    <div class="msg10" v-if="contador == 10">O número é 10.</div>
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
  background-color: white;
  border: 0;
  border-radius: 10px;
  color: black;
  margin-left: 10px;
  margin-top: 15px;
  margin-left: 20px;
}

button:hover {
  background-color: grey;
}

.info {
  background-color: rgb(0, 0, 0);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 20px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em; 
}

.contador {
  background-color: black;
  border-radius: 20px;
  margin-left: 10px;
  
}

template {
  background-color: red;
}

.msgRed {
  background-color: rgb(194, 71, 71);
  margin-top: 10px;
  color: black;
  text-align: center;
  width: 50%;
  border-radius: 10px;
  margin-left: 25%;
}
.msgGreen {
  background-color: rgb(72, 153, 72);
  margin-top: 10px;
  color: black;
  text-align: center;
  width: 50%;
  margin-left: 25%;
  border-radius: 10px;
}

.msg10 {
  background-color: rgb(127, 153, 80);
  margin-top: 10px;
  color: black;
  text-align: center;
  width: 50%;
  margin-left: 25%;
  border-radius: 10px;
}
</style>
