<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>

    <div>
      <input type="number" v-model.number="numero1" placeholder="Digite o primeiro número">
      <select v-model="operacao">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="numero2" placeholder="Digite o segundo número">
    </div>

    <div>
      <h3>Resultado: {{ resultado }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+'
    }
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2;
        case '-':
          return this.numero1 - this.numero2;
        case '*':
          return this.numero1 * this.numero2;
        case '/':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    }
  }
}
</script>

<style scoped>
#app {
  text-align: center;
  margin-top: 50px;
}

input, select {
  margin: 5px;
  padding: 5px;
  font-size: 16px;
}

h3 {
  margin-top: 20px;
}
</style>
