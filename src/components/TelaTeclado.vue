<template>
  <div class="teclado">
    <button
      class="teclado-botao"
      v-for="(letra, key) in 'abcdefghijklmnopqrstuvwxyz'"
      :key="key"
      :disable="verificarLetra(letra)"
      v-on:click="jogar(letra)"
    >
      {{ letra }}
    </button>
  </div>
</template>

<script>
export default {
  name: "TelaTeclado",
  props: {
    letras: Array,
    verificarLetra: Function,
    jogar: Function,
  },
};
</script>

<style>
.teclado {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 80%;
  margin-top: 20px;
}
.teclado-botao {
  margin: 5px;
  text-transform: uppercase;
}
</style>
