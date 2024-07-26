<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div>
      <input type="number" v-model.number="num1" placeholder="Número 1" />
      <select v-model="operacao">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="num2" placeholder="Número 2" />
    </div>
    <div>
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
    };
  },
  computed: {
    resultado() {
      let res = 0;
      switch (this.operacao) {
        case '+':
          res = this.num1 + this.num2;
          break;
        case '-':
          res = this.num1 - this.num2;
          break;
        case '*':
          res = this.num1 * this.num2;
          break;
        case '/':
          res = this.num2 !== 0 ? this.num1 / this.num2 : 'Erro: Divisão por zero';
          break;
      }
      return res;
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
input, select {
  margin: 5px;
}
</style>
