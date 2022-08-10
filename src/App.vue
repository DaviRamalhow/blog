<template>

  <div id="app">
    <ul>
      <li v-for="(cor, i) in cores" :key="cor">{{ i + 1 }}) {{ cor }}</li>
    </ul>
    <ul>
      <button @click="cores.push('branca')">Adicionar</button>
      <li v-for="pessoa in pessoas" :key="pessoa">
        <div v-for="(valor, chave, index) in pessoa" :key="valor">
          {{ chave }} = {{ valor }} ({{ index + 1 }})
        </div>
      </li>
    </ul>
    <hr>
    <span v-for="n in 10" :key="n">{{ n }}</span>
  </div>
</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>
import { ref } from "vue";
const cores = ref([
  'vermelho',
  'verde',
  'amarelo',
  'azul',
  "roxo",
  "aqua"
])

const pessoas = ref([
  { nome: "Ana", idade: 26, peso: 59 },
  { nome: "Guilherme", idade: 22, peso: 89 }
])
</script>



<!--================ STYLE ================-->
<style>
#app {
  font-family: 'Courier New', Courier, monospace;
  display: flex;
}

ul {
  list-style: none;
}
</style>