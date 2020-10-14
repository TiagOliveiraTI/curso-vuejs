<template>
  <div
    :class="{
      'div-cliente-premium': cliente.isPremium,
      'div-cliente': !cliente.isPremium,
    }"
  >
    <h4>Nome: {{ cliente.nome }}</h4>
    <p>{{ cliente.email | processarEmail}}</p>
    <p v-if="cliente.showAge === true">{{ cliente.idade }}</p>
    <p v-else>Esse usuário optou por esconder a idade</p>
    <button @click="mudarCor($event)">Muda cor</button>
    <button @click="emitirEventoDelete()">Excluir</button>
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
      mudarCor: function() {
        this.cliente.isPremium = !this.cliente.isPremium; 
      },
      emitirEventoDelete: function() {
        console.log("emitirEventoDelete do filho")
        this.$emit("meDeletaPapai", {idDoCliente: this.cliente.id, 'teste': 'Testando passar qualquer coisa', component: this})
      },
      testar: function() {
        console.log("Testando um metodo de filho passado para pai")
      }
  },
  filters: {
    processarEmail: function(value) {
      return value.toUpperCase()
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