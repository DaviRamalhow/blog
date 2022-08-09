<template>

  <div id="app">
    <div id="caixas">
      <div class="demo" :class="estilo1" @click="aplicarC1 = !aplicarC1"></div>
      <br>
      <div class="demo2"></div>
      <br>
      <div class="demo3" :class="[classeCSS, { girar: aplicarGirar }]"></div>
    </div>
    <hr>
    <input type="text" v-model="classeCSS">
  </div>
</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>
import { ref, computed } from "vue";
const aplicarC1 = ref(false);
const classeCSS = ref("c1");
const aplicarGirar = ref(true);


const estilo1 = computed(() => {
  return {
    c1: aplicarC1.value,
    c2: !aplicarC1.value,
  }
})

</script>



<!--================ STYLE ================-->
<style>
#caixas {
  font-family: 'Courier New', Courier, monospace;
  display: flex;
  justify-content: space-between;
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

.demo {
  margin-left: 1.75rem;
  width: 100px;
  height: 100px;
  background-color: rgb(59, 59, 59);
}

.demo2 {
  margin-left: 1.75rem;
  width: 100px;
  height: 100px;
  background-color: rgb(59, 59, 59);
}

.demo3 {
  margin-left: 1.75rem;
  width: 100px;
  height: 100px;
  background-color: rgb(59, 59, 59);
}

.c1 {
  background-color: red;
}

.c2 {
  background-color: green;
}

.c3 {
  background-color: blue;
}

.girar {
  transform: rotate(45deg);
}
</style>
