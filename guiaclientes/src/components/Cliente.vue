<template>
    <div id="div-cliente">
        <input type="text" :value="nome">
        <hr>
        <input type="text" :value="descricao">
        <h2>Olá {{nome}}!</h2>
        <p>Descrição: {{descricao}}</p>

    </div>
</template>

<script>
export default {
    data() {
        return {
            nome: "Tiago ",
            numero: "",
            email: "",
            idade: 0,
            descricao: "lorem ipsum dolor sit amet, consectetur adipiscing",
        }
    }
}
</script>

<style scoped>

</style>