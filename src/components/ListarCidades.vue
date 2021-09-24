<template>
  <ul>
    <li
      v-for="(cidade, index) in cidades"
      :key="index"
      :class="{ removed: cidade.checked }"
    >
      <input type="checkbox" v-model="cidade.checked" />
      <label>{{ cidade.titulo }}</label>
      </li>
    </ul>
</template>

<script>
export default {
    props: {
        cidades: {
            type: Array,
            default() {
                return [{ titulo: "Cidade padrão", checked: false }];
            }


        }
    }
}
</script>

<style>

</style>