<template>
  <div
    :class="{
      'div-cliente-premium': cliente.isPremium,
      'div-cliente': !cliente.isPremium,
    }"
  >
    <h4>Nome: {{ cliente.nome }}</h4>
    <p>{{ cliente.email }}</p>
    <p v-if="cliente.showAge === true">{{ cliente.idade }}</p>
    <p v-else>Esse usuário optou por esconder a idade</p>
    <button @click="mudarCor($event)">Muda cor</button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    cliente: Object,
    showAge: Boolean,
  },
  methods: {
      mudarCor: function($event) {
        console.log($event)
        this.cliente.isPremium = !this.cliente.isPremium; 
      }
  }
};
</script>

<style scoped>
.div-cliente {
  background-color: #e6e6e6;
  padding: 1%;
  margin: 2% 0;
}

.div-cliente-premium {
  background-color: black;
  color: gold;
  padding: 1%;
  margin: 2% 0;
}
</style>