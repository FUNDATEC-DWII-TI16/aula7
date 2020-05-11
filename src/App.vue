<template>
  <div id="app">
    <button class="btn btn-primary" @click="computarClick()">Click me</button>
    <div>Onde machucou: {{ localDoUltimoMachucado }}</div>
    <div>Quantidade Mertiolate: {{ quantidadeMertiolate }}</div>
    <hr />
    <filho
      :quantidade-clicks-do-pai="quantidadeClicks"
      @machucou="passarMertiolate($event)"
    />
  </div>
</template>

<script>
import Filho from "./components/Filho.vue";

export default {
  name: "App",
  components: {
    Filho,
  },
  data() {
    return {
      quantidadeClicks: 0,
      quantidadeMertiolate: 0,
      localDoUltimoMachucado: null,
    };
  },
  methods: {
    computarClick() {
      this.quantidadeClicks++;
    },
    passarMertiolate(informacoesDoEvento) {
      this.quantidadeMertiolate++;
      alert("buaaaaaa, " + informacoesDoEvento.localDoMachucado);
      this.localDoUltimoMachucado = informacoesDoEvento.localDoMachucado;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
