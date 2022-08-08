<template>

  <div id="app">

    <p v-once>{{ title }}</p> {{ dia }} <br> {{ saudacao() }}

    <input type="text" v-model="title">
    <input type="text" v-model="dia">
    <input type="text" v-model="nome">
    <br>
    <a v-bind:href="link">google</a>

    <br>
    <p v-html="linkHtml"></p>

    <br>
    <br>
    <p>Usando VueJS - {{ nome }} ({{ idade }})</p>
    <p>{{ mutiply() }}</p>
    <p>{{ random() }}</p>
    <br>
    <img height="400" v-bind:src="imagem">
  </div>
</template>
<!--================ END TEMPLATE ================-->


<!--================ SCRIPT ================-->
<script setup>
import { ref } from "vue";
//import { data } from "./utils";

const title = ref("Usando VuesJS 3");
const dia = ref("dia 30");
const link = ref("http://google.com.br");
const linkHtml = ref('<a v-bind:href="link">google</a>');
const nome = ref("Davi");
const idade = ref("17");
const imagem = ref("https://i.pinimg.com/originals/d5/d4/3a/d5d43a7dceef16619122735e7800ca08.jpg");

const saudacao = () => {
  title.value = "Boa semana";
  return title.value;
}

const mutiply = () => {
  let idade3 = idade.value * 3;
  return idade3;
}

const random = () => {
  let x = Math.random() * (0, 1);
  return x;
}
</script>

<!--================ STYLE ================-->
<style>
#app {

  font-family: 'Courier New', Courier, monospace;
}

input {
  text-align: center;
  font-family: sans-serif;
  background-color: rgb(212, 167, 255);
  border-radius: 10px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  border-color: transparent;
  margin-left: 0.5rem;
}
</style>
