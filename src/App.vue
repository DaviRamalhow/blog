<template>

  <div id="app">

    <div v-if="altern">

      <p>Voce quer me ver ...</p>
      <p>... ou eu</p>

    </div>
    <div v-else>
      <p>Voce quer me ver...</p>
      <p>...ou eu aqui</p>
    </div>

    <button @click="altern = !altern">Alternar</button>

    <ul>
      <li v-for="livru in livro" :key="livru">
        <div v-for="(valor, chave, index) in livru" :key="valor">
          {{ chave }} = {{ valor }} ({{ index + 1 }})
        </div>
      </li>
      <br>
      <li v-for="pessoa in aluno" :key="pessoa">
        <div v-for="(valor, chave, index) in pessoa" :key="valor">
          {{ chave }} = {{ valor }} ({{ index + 1 }})
        </div>
      </li>
      <br>
      <li v-for="cup in copo" :key="cup">
        <div v-for="(valor, chave, index) in cup" :key="valor">
          {{ chave }} = {{ valor }} ({{ index + 1 }})
        </div>
      </li>
      <br>

      <ul>
        <li v-for="pessoa in alune" :key="pessoa">
          <template v-if="!Array.isArray(pessoa)">
            {{ pessoa }}
          </template>
          <template v-else>
            notas:
            <ul>
              <li v-for="nota in pessoa" :key="nota">
                {{ nota }}
              </li>
            </ul>
          </template>
        </li>
      </ul>

    </ul>
  </div>

</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>

import { ref } from "vue";
const altern = ref(false);
const livro = ref([

  { titulo: "O senhor dos aneis", autor: "J.R.R. Tolkiens" }

])
const aluno = ref([

  { id: 10, nome: "Maria", notas: [7.67, 8.33, 6.98, 9.21] }

])
const alune = ref(

  { id: 10, nome: "Maria", notas: [7.67, 8.33, 6.98, 9.21] }

)
const copo = ref([

  { tamaho: "grande", cor: "amarelo", mls: 600 }

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