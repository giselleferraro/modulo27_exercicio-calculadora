<script>
import Calculadora from './components/Calculadora.vue';

export default {
  // name: 'App',
  components: {
    Calculadora,
  },
};
</script>

<template>
<div class="container" id="calculadora">
  <Calculadora />
</div>
</template>

<style>
  .container {
  margin: 0 auto;
  padding: 20px;
  background-color: rgba(203, 174, 230, 0.925);
  }
</style>