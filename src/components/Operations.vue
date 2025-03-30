<script setup>
const props = defineProps(['calculo', 'estado']);

</script>

<template>
    <h1>Calculadora Aritmética</h1>
    <form>
        <input type="number" id="valor-a" placeholder="Valor A" required v-model="props.estado.valorA"
            @input="props.calculo">
        <input type="number" id="valor-b" placeholder="Valor B" required v-model="props.estado.valorB"
            @input="props.calculo">
    </form>
    <select title="Alterar operador" v-model="props.estado.operador" @change="props.calculo">
        <option value="adicao">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
        <option value="resto">%</option>
    </select>
</template>

<style scoped>
* {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    font-family: sans-serif;
    list-style: none;
    color: #FFF;
    border: none;
    outline: none;
    cursor: default;
}

h1 {
    margin: 20px 0 40px;
    color: goldenrod;
}

input {
    width: 120px;
    height: 60px;
    text-align: center;
    font-size: 20px;
    font-weight: 600;
    margin: 0 30px 30px;
    border: 2px solid gold;
    border-radius: 8px;
    background-color: #000;
    color: #fff;
    letter-spacing: 1px;
    transition: .3s;
    cursor: text;
}

input::placeholder {
    color: #ffffffab;
    font-weight: 400;
}

input:focus {
    background-color: rgba(255, 217, 0, 0.3);
    border-radius: 2px;
}

input:focus::placeholder {
    color: transparent;
}

input:hover {
    border-radius: 2px;
}

select {
    background-color: goldenrod;
    opacity: .8;
    color: #FFF;
    font-size: 30px;
    font-weight: 800;
    text-align: center;
    width: 60px;
    height: 60px;
    border-radius: 50px;
    -webkit-appearance: none;
    cursor: pointer;
    transition: .5s;
}

select:hover,
select:focus {
    opacity: 1;
    border-radius: 20px;
    text-shadow: 1px 2px 3px rgba(0, 0, 0, .5);
}
</style>