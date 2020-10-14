<template>
  <div id="app">
    <h1>Guia de Clientes</h1>
    <Cliente :cliente="clienteTiago" :showAge="true"/>
    <Cliente :cliente="clienteArielle" :showAge="false"/>
    <!-- <Cliente nome="Iris Oliveira" email="irisocsilva@gmail.com" idade="10"/>
    <Cliente nome="Arthur Oliveira" email="arthuroliveiracsilva@gmail.com" idade="8"/>
    <Cliente nome="Henri Oliveira" email="henriocsilva@gmail.com" idade="3"/> -->
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
      clienteTiago: {
        nome: 'Tiago Oliveira',
        idade: 32,
        email: 'dev.tiago.oliveira@gmail.com'
      },
      clienteArielle: {
        nome: 'Arielle P C Silva',
        idade: 29,
        email: 'arielle.carmo@gmail.com',
        isPremium: true
      }
    }
  }
}
</script>

<style>

</style>
