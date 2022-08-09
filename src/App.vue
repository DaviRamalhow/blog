<template>

  <div id="app">

    <button @click="aumentar">aumentar</button>
    <button @click="dimuir">dimuir</button>
    <p>Contador: {{ Contador }}</p>
    <p>Resultado: {{ resultado() }}</p>
    {{ mutiplicado }}
  </div>
</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>
import { ref, computed, watch } from "vue";
//import { data } from "./utils";

const Contador = ref(0);
const mutiplicado = computed(() => {
  return Contador.value * 2;
})

const aumentar = () => {
  Contador.value++;
  //Resultado.value = Contador.value >= 5 ? "Maior ou igual a 5" : "Menor que 5";
}
const dimuir = () => {
  Contador.value--;
  // Resultado.value = Contador.value >= 5 ? "Maior ou igual a 5" : "Menor que 5";
}
const resultado = () => {
  return Contador.value >= 5 ? "Maior ou igual a 5" : "Menor que 5";
}
watch(Contador, () => {
  setTimeout(() => {
    Contador.value = 0;
  }, 5000)
})
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
