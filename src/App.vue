<template>

  <div id="app">

    <div v-if="logado">
      <p>Usuario Logado: {{ nome }}</p>
      <p>Perfil: Admin</p>
    </div>

    <p v-else-if="anonimo">Navegando anonimamente</p>
    <p v-else>Nennhum usaurio logado</p>

    <button @click="logado = !logado">{{ logado ? "Sair" : "Entrar" }}</button>
    <input type="checkbox" v-model="anonimo">
  </div>
</template>
<!--================ END TEMPLATE ================-->



<!--================ SCRIPT ================-->
<script setup>
import { ref } from "vue";
const nome = ref("Maria");
const logado = ref(false);
const anonimo = ref(false);

</script>



<!--================ STYLE ================-->
<style>
#app {
  font-family: 'Courier New', Courier, monospace;
  display: flex;
}
</style>