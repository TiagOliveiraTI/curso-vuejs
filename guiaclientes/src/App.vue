<template>
  <div id="app">
    <h1>Guia de Clientes</h1>
    <input type="text" v-model="nomeDoTiago">
    <Cliente :nome="nomeDoTiago" email="dev.tiago.oliveira@gmail.com" idade="32"/>
    <Cliente :cliente="clienteArielle"/>
    <Cliente nome="Iris Oliveira" email="irisocsilva@gmail.com" idade="10"/>
    <Cliente nome="Arthur Oliveira" email="arthuroliveiracsilva@gmail.com" idade="8"/>
    <Cliente nome="Henri Oliveira" email="henriocsilva@gmail.com" idade="3"/>
  </div>
</template>

<script>

import Cliente from './components/Cliente';


export default {
  name: 'App',
  components: {
    Cliente
  },
  data(){
    return {
      nomeDoTiago: 'Tiago Aparecido de Oliveira',
      clienteArielle: {
        nome: 'Arielle P C Silva',
        idade: 29,
        email: 'arielle.carmo@gmail.com'
      }
    }
  }
}
</script>

<style>

</style>
