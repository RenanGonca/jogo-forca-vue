<template>
  <div class="jogo">
    <TelaForca :erros="erros" />
    <TelaPalavra
      :palavra="palavra"
      :dica="dica"
      :verificar-letra="verificarLetra"
      :etapa="etapa"
    />

    <TelaTeclado
      v-if="etapa === 'jogo'"
      :letras="letras"
      :verificar-letra="verificarLetra"
      :jogar="jogar"
    />

    <TelaFinal
      v-if="etapa != 'jogo'"
      :etapa="etapa"
      :texto="etapa === 'ganhador' ? 'Parabéns :)' : 'Tadinho :('"
      :jogarNovamente="jogarNovamente"
    />
  </div>
</template>

<script>
import TelaForca from "./TelaForca.vue";
import TelaPalavra from "./TelaPalavra.vue";
import TelaTeclado from "./TelaTeclado.vue";
import TelaFinal from "./TelaFinal.vue";

export default {
  name: "TelaJogo",
  props: {
    erros: Number,
    palavra: String,
    dica: String,
    verificarLetra: Function,
    etapa: String,
    letras: Array,
    jogar: Function,
    jogarNovamente: Function,
  },
  components: {
    TelaForca,
    TelaPalavra,
    TelaTeclado,
    TelaFinal,
  },
};
</script>

<style>
.jogo {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
</style>
