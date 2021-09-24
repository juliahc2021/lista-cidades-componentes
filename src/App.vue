<template>
  <section>
    <cabecalho :valor="titulo" />
    <div class="container">
      <adicionar-cidade v-on:adicionarCidade="adicionarCidade" />
      <listar-cidades :cidades="cidades" />
      <altera>
        <em>Altere aqui o título da sua lista de cidades</em>
        <entrada-dados v-model="titulo" type="text" />
      </altera>
    </div>
    <rodape />
  </section>
</template>

<script>
import Cabecalho from "@/components/Cabecalho";
import Rodape from "@/components/Rodape";
import ListarCidades from "@/components/ListarCidades";
import AdicionarCidade from "@/components/AdicionarCidade";
import EntradaDados from "@/components/templates/EntradaDados";

export default {
  name: "App",
  components: { Cabecalho, Rodape, ListarCidades, AdicionarCidade, EntradaDados },
  data() {
    return {
      titulo: "Lista de cidades",
      novaCidade: "",
      cidades: [
        { titulo: "Joinville", checked: false },
        { titulo: "Rio de Janeiro", checked: true },
      ],
    };
  },
  methods: {
    adicionarCidade(novaCidade) {
      this.cidades.push({
        titulo: novaCidade,
        checked: false,
      });
    },
  },
};
</script>

<style>

.container {
  width: 40%;
  margin: 20px auto 0px auto;
}

ul li {
  list-style: none;
}

.removed {
  color: gray;
}

.removed label {
  text-decoration: line-through;
}
</style>
