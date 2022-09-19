<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      resultado: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https://www.cepaberto.com/api/v3/cep?cep=$(this.cep)`;
      this.resultado = await axios.get(url, {
        headers: {
          Authorization: "Token token=331b1ae99ca3314578e820ab16402077",
        },
      });
    },
  },
};
</script>
<template>
  <div class="container">
    <h1>CEPADOR DE CASA C:</h1>
    <form @submit.prevent="search">
      <input placeholder="Insira o cep aqui" type="text" v-model="cep" />
      <button type="submit">Buscar</button>
    </form>
  </div>
</template>
<style>
.container {
  padding: 10%;
  background-color: rgb(88, 255, 191);
  color: rgb(0, 0, 0);
}
</style>
