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
    <br>
    <button @click="iniciarEfeito">iniciar Efeito</button>
    <div id="efeito" :class="aplicarClasse"></div>
    <br>
    <input type="text" v-model="classse">
    <div :class="classse"></div>
    <br>
    <div :class="[{ x }, 'destaque']">Estou sem classe CSS :(</div>
    <br>
    <br>
    <input type="text" v-model="classe1">
    <input type="text" @input="setStyle">
    <div :class="[classe1, { demo }]"></div>
    <br>
    <br>
    <input type="text" v-model="cor1">
    <div :style="[estilo1, { backgroundColor: cor1 }]"> </div>
    <br>
    <br>
    <button @click="iniciarProgresso">Iniciar</button>
    <div class="barra-progresso">
      <div class="progresso" :style="{ width }"></div>
    </div>
  </div>
</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>
import { ref, computed } from "vue";

const cor = ref("red");
const largura = ref(100);
const altura = ref(40);
const aplicarClasse = ref("destaque");
const x = ref(true);
const demo = ref("demo")
const classse = ref("");
const classe1 = ref("");
const cor1 = ref("");
const estilo1 = ref({
  width: '100px',
  height: '100px',
})
const width = ref(0);


const meuEstilo = computed(() => {
  return {
    "background-color": cor.value,
    width: largura.value + 'px',
    height: altura.value + 'px'
  }
})
const iniciarEfeito = () => {

  setInterval(() => {

    aplicarClasse.value = aplicarClasse.value == "destaque" ? "encolher" : "destaque";
  }, 1000)
}

const setStyle = (event) => {
  if (event.target.value == "true") {
    demo.value = true;
  } else if (event.target.value == "false") {
    demo.value = false;
  }
}
const iniciarProgresso = () => {

  let valor = 0;
  const temporizador = setInterval(() => {
    valor += 5;
    width.value = `${valor}%`;
    if (valor == 100) clearInterval(temporizador);
  }, 500)

}
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
  margin-top: 2rem;
  margin-left: 1.75rem;
  width: 100px;
  height: 100px;
  background-color: rgb(233, 127, 127);
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

#efeito {
  width: 100px;
  height: 100px;
  border: 1px solid black;
}

.destaque {
  background-color: red;
  width: 200px !important;
}

.encolher {
  border: 1px solid black;
  width: 50px;
  height: 50px;
}

.x {
  background-color: aqua;
  width: 400px;
  height: 100px;
}

.y {
  background-color: darkblue;
  width: 100px;
  height: 400px;
}

.barra-progresso {
  height: 30px;
  width: 500px;
  border: 1px solid black;
}

.progresso {
  background-color: red;
  height: 100%;
}
</style>