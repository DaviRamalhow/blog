<template>

  <div id="app">
    <div id="caixas">
      <div class="demo" :style="{ backgroundColor: cor }"></div>
      <br>
      <div class="demo2" :style="[meuEstilo]"></div>
      <br>
      <div class="demo3"></div>
    </div>
    <hr>
    <input type="text" v-model="cor">
    <input type="text" v-model="largura">
    <input type="text" v-model="altura">
  </div>
</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>
import { ref, computed } from "vue";
const cor = ref("red");
const largura = ref(100);
const altura = ref(40);
const meuEstilo = computed(() => {
  return {
    "background-color": cor.value,
    width: largura.value + 'px',
    height: altura.value + 'px'
  }
})
// const v = { "background-color": cor.value }

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
