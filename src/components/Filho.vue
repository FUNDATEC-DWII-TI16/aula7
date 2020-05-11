<template>
  <div class="hello">
    Filho {{ propriedadeDoFilho }} Clicks do pai: {{ quantidadeClicksDoPai }}
    <button @click="avisarPaiQueSeMachucou()">Ouch!</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      propriedadeDoFilho: 123,
    };
  },
  props: {
    quantidadeClicksDoPai: Number,
  },
  methods: {
    avisarPaiQueSeMachucou() {
      this.$emit("machucou", { localDoMachucado: "ralou o joelho" });
    },
  },
};
</script>
