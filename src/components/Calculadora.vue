<script setup>
import { reactive } from 'vue';

const estado = reactive({
    numeroA: '',
    numeroB: '',
    operacoes: {
        soma: (a, b) => a + b,
        subtracao: (a, b) => a - b,
        multiplicacao: (a, b) => a * b,
        divisao: (a, b) => (b !== 0 ? a / b : 'Erro - Não é possível dividir por zero'),
    },
    resultado: 0,
});

const resultado = () => {
    const { numeroA, numeroB, operacaoMat } = estado;
    estado.resultado = estado.operacoes[operacaoMat](parseFloat(numeroA), parseFloat(numeroB));
};
</script>

<template>
    <div>
        <h1 class="titulo">Calculadora Aritmética</h1>
        <input required placeholder="Digite um valor" type="number" class="form-control"  v-model="estado.numeroA" @input="resultado" />
        <input required placeholder="Digite um valor" type="number" class="form-control mt-2" v-model="estado.numeroB" @input="resultado" />

        <select class=" form-control mt-2" v-model="estado.operacaoMat" @change="resultado">
            <option value="soma">Soma</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
        </select>

        <p class="results">Seu resultado é:
        <br />
        {{ estado.resultado }} </p>
    </div>
</template>

<style scoped>
.results {
    font-size: 20px;
    margin-top: 10px;
    display: flex;
    text-align: center;
    justify-content: center;
    color: blueviolet;
}

.titulo{
    font-size: 50px;
    color: blueviolet;
    margin-top: 10px;
    margin-bottom: 10px;
    display: flex;
    text-align: center;
    justify-content: center;
}
</style>