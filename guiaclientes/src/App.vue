<template>
  <div id="app">
    <h1>Guia de Clientes</h1>
    <div v-for="cliente in clientes" :key="cliente.id">
      <Cliente :cliente="cliente" />
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente";

export default {
  name: "App",
  components: {
    Cliente,
  },
  data() {
    return {
      clientes: [
        {
          id: 1,
          nome: "Tiago Oliveira",
          idade: 32,
          showAge: false,
          email: "dev.tiago.oliveira@gmail.com",
        },
        {
          id: 2,
          nome: "Arielle P C Silva",
          idade: 29,
          showAge: false,
          email: "arielle.carmo@gmail.com",
          isPremium: true,
        },
        {
          id: 3,
          nome: "Iris de Oliveira",
          idade: 10,
          showAge: true,
          email: "irisocsilva@gmail.com",
        },
        {
          id: 4,
          nome: "Arthur de Oliveira",
          idade: 8,
          showAge: true,
          email: "irisocsilva@gmail.com",
        },
        {
          id: 5,
          nome: "Henri de Oliveira",
          idade: 3,
          showAge: true,
          email: "irisocsilva@gmail.com",
          isPremium: true,
        },
      ],
    };
  },
};
</script>

<style>
</style>
