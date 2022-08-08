<template>

  <div id="app">

    <p v-once>{{ title }}</p>

    <input type="text" v-model="title">

  </div>
</template>
<!--================ END TEMPLATE ================-->


<!--================ SCRIPT ================-->
<script setup>
import { ref } from "vue";
//import { data } from "./utils";

const title = ref("Usando VuesJS 3");


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
