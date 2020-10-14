<template>
    <div id="div-cliente">
        <h4>Nome: {{cliente.nome}}</h4>
        <p>{{cliente.email}}</p>
        <p v-if="showAge === true">{{cliente.idade}}</p>
        <p v-else>Esse usuário optou por esconder a idade</p>
    </div>
</template>

<script>
export default {
    data() {
        return {

        }
    },
    props: {
        cliente: Object,
        showAge: Boolean,
    }
}
</script>

<style scoped>
    #div-cliente {
        background-color: #e6e6e6;
        padding: 1%;
        margin: 2% 0;
    }
</style>