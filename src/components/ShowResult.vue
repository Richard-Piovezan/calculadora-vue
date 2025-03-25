<script setup>
const props = defineProps(['resultado', 'resultadoAnterior']);
</script>

<template>
    <div class="result">
        <h2>RESULTADOS</h2>
        <span class="new_result">
            O resultado da operação foi:
            <span class="new_result_value"> {{ props.resultado }} </span>
        </span>
        <hr>
        <span class="past_result">
            O resultado da operação anterior foi:
            <span class="past_result_value"> {{ props.resultadoAnterior }} </span>
        </span>
    </div>
</template>

<style scoped>
.result {
    background-color: rgba(155, 155, 155, .2);
    padding: 8px 16px;
    margin-top: 40px;
    display: flex;
    flex-direction: column;
    font-size: 20px;
}

h2 {
    font-size: 24px;
    margin: 20px 0 40px;
    color: goldenrod;
}

.new_result {
    display: flex;
    justify-content: center;
    letter-spacing: 1px;
    align-items: center;
}

.new_result_value {
    margin-left: 8px;
    font-size: 24px;
    color: goldenrod;
}

.past_result {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 14px;
    font-size: 16px;
    letter-spacing: 1px;
    color: #cdcdcd;
}

.past_result_value {
    margin-left: 6px;
    font-size: 18px;
    color: #cdcdcd;
}

hr {
    border: 1px solid rgba(255, 255, 255, 0.137);
    width: 100%;
    margin: 16px 0 4px;
}
</style>