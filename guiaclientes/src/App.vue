<template>
  <div id="app">
    <h3>Cadastro:</h3>
    <small class="nomeErro" v-show="deuErro">O nome é inválido!, Tente novamente</small><br>
    <input type="text" name=""  id="" placeholder="Nome Completo" v-model="nomeField"><br>
    <input type="email" name=""  id="" placeholder="E-mail" v-model="emailField"><br>
    <input type="number" name="" id="" placeholder="idade" v-model="idadeField"><br>
    <button @click="cadastrarUsuario">Cadastrar</button>
    <hr>
    <h1>Guia de Clientes</h1>
    <div v-for="cliente in clientes" :key="cliente.id">
      <Cliente :cliente="cliente" @meDeletaPapai="deletarUsuario($event)"/>
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
  methods: {
    cadastrarUsuario: function() {
      if (this.nomeField === "" || this.nomeField === " " || this.nomeField.length < 3) {
        this.deuErro = true;
      } else {
        this.clientes.push({
          nome: this.nomeField,
          email: this.emailField,
          idade: this.idadeField,
          id: Date.now()
        });
        this.nomeField = '';
        this.emailField = '';
        this.idadeField = 0;
        this.deuErro = false;
      }
    },
    deletarUsuario: function ($event) {
      let id = $event.idDoCliente;
      let novoArray = this.clientes.filter(cliente => cliente.id != id)
      this.clientes = novoArray;
    }
  },
  data() {
    return {
      deuErro: false,
      nomeField : '',
      emailField : '',
      idadeField : 0,
      clientes: [
        {
          id: 1,
          nome: "Tiago Oliveira",
          idade: 32,
          showAge: false,
          email: "dev.tiago.oliveira@gmail.com",
          isPremium: false,
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
          isPremium: false,
        },
        {
          id: 4,
          nome: "Arthur de Oliveira",
          idade: 8,
          showAge: true,
          email: "irisocsilva@gmail.com",
          isPremium: true,
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
  .nomeErro {
    color: red
  }
</style>
