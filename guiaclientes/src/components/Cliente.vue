<template>
    <div id="div-cliente">
        <h4>Nome: {{cliente.nome}}</h4>
        <p>{{cliente.email}}</p>
        <p>{{cliente.idade}}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {

        }
    },
    props: {
        nome: String,
        email: String,
        idade: Number,
        cliente: Object

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