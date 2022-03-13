<template>
  <ClubesTabela :clubes="clubesOrdenados" />
</template>

<script>
import ClubesTabela from "../components/ClubesTabela.vue";

export default {
  name: "ClubesLista",
  components: { ClubesTabela },
  data: () => ({
    lista: [],
  }),
  created() {
    fetch("https://hackthon-decola.firebaseio.com/clubes-lista.json")
      .then((response) => response.json())
      .then((data) => (this.lista = data));
  },
  computed: {
    clubesOrdenados() {
      const listaComputada = this.lista
        .slice(0)
        .sort((a, b) => (a.pontos > b.pontos ? -1 : 1));
      return listaComputada;
    },
  },
};
</script>

<style>
</style>