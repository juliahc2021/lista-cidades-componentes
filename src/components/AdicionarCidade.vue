<template>
        <div class="input-group">
        <!-- <entrada-dados :value="novaCidade" @input="associarValor" /> -->
        <entrada-dados @salvar="adicionarCidade" v-model="novaCidade" />
        <span class="input-group-btn">
          <button @click="adicionarCidade" class="btn btn-primary">
            Adicionar Cidade
          </button>
        </span>
      </div>

</template>

<script>
import EntradaDados from '@/components/templates/EntradaDados'
export default {
  components: { EntradaDados },
    data () {
        return {
            novaCidade: "",
        }
    },
    methods: {
        adicionarCidade() {
            this.$emit("adicionarCidade", this.novaCidade);
            this.novaCidade = "";
        },
        // associarValor(valor) {
        //  this.novaCidade = valor;
       // }
    }

}
</script>

<style>

</style>