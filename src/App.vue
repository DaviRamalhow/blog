<template>

  <div id="app">

    <p>{{ contador }}</p>
    <button @click="somar(3)">Somar 1</button>
    <p @mousemove="mouseMove">Mouse:{{ x }} e {{ y }}
      <span @mousemove.stop="mousemove">PARAR AQUI!!!!!!</span>
    </p>
    <hr>
    <input type="text" @keyup.enter="exibirAlerta">
    <br>
    <br>

    <button @click="exibirAlerta">Exibir alerta</button>
    <input type="text" @keydown.enter="data = $event.target.value">
    <p>{{ data }}</p>

  </div>
</template>
<!--================ END TEMPLATE ================-->


<!--================ SCRIPT ================-->
<script setup>
import { ref } from "vue";
//import { data } from "./utils";

const contador = ref(0);
const x = ref(0);
const y = ref(0);

const mouseMove = (event) => {
  x.value = event.clientX;
  y.value = event.clientY;
  console.log(event.clientX, event.clientY);
}

const somar = (X, ev) => {

  console.log(x, ev);
  contador.value = contador.value + X;
}
const exibirAlerta = () => {
  alert("estou te alertando");
}

const data = ref(0);
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
