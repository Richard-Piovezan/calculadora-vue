<script setup>
import { reactive } from 'vue';
import Operation from './components/Operations.vue';
import ShowResult from './components/ShowResult.vue';

const estado = reactive({
  valorA: 0,
  valorB: 0,
  operador: "adicao",
  resultado: 0,
  resultadoAnterior: null
})

const calcular = () => {
  let resultadoCalculo = 0;

  if (estado.operador === "adicao") {
    resultadoCalculo = parseFloat(estado.valorA) + parseFloat(estado.valorB);
  } else if (estado.operador === "subtracao") {
    resultadoCalculo = parseFloat(estado.valorA) - parseFloat(estado.valorB);
  } else if (estado.operador === "multiplicacao") {
    resultadoCalculo = parseFloat(estado.valorA) * parseFloat(estado.valorB);
  } else if (estado.operador === "divisao" && estado.valorB != 0) {
    resultadoCalculo = parseFloat(estado.valorA) / parseFloat(estado.valorB);
  } else if (estado.operador === "resto" && estado.valorB != 0) {
    resultadoCalculo = parseFloat(estado.valorA) % parseFloat(estado.valorB);
  }else {
    resultadoCalculo = "Erro"
  }

  estado.resultadoAnterior = estado.resultado;
  estado.resultado = resultadoCalculo;
}
</script>

<template>
  <div class="container">
    <Operation :valor-a="estado.valorA" :valor-b="estado.valorB" :operador="estado.operador" :calculo="calcular"/>
    <ShowResult :resultado="estado.resultado" :resultado-anterior="estado.resultadoAnterior" />
  </div>
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

  .container {
    background-color: #000;
    border: 3px solid #fff;
    padding: 40px;
    width: 600px;
    text-align: center;
    border-radius: 20px;
  }

  @media (max-width: 768px) {
    .container {
      width: 100%;
      padding: 12px;
    }
  }
</style>