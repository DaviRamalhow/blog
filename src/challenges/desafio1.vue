<template>
    <p>Usando VueJS - {{ nome }} ({{ idade }})</p>

</template>


<script setup>
import { ref } from "vue";

const nome = ref("Davi");
const idade = ref("17");

</script>


<style>
</style>