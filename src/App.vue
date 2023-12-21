<template>
  <div id="app" class="container mt-5">
    <h1>Calculadora Vue.js</h1>
    <div class="row">
      <div class="col-md-4">
        <label for="numero1" class="form-label">Número 1:</label>
        <input v-model="numero1" type="number" class="form-control form-control-sm" @input="calcularResultado" />
      </div>
      <div class="col-md-4">
        <label for="operacao" class="form-label">Operação:</label>
        <select v-model="operacao" class="form-select form-select-sm" @change="calcularResultado">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">x</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="col-md-4">
        <label for="numero2" class="form-label">Número 2:</label>
        <input v-model="numero2" type="number" class="form-control form-control-sm" @input="calcularResultado" />
      </div>
    </div>
    <div class="mt-3">
      <h3>Resultado: {{ resultado }}</h3>
    </div>
    <div>
      <button class="btn btn-primary" @click="limpar">Limpar</button>
    </div>
  </div>
</template>

<script>
export default
{
  data()
  {
    return {
      numero1: 0,
      operacao: '',
      numero2: 0,
      resultado: 0,
    };
  },
  methods:
  {
    calcularResultado()
    {
      switch (this.operacao)
      {
        case '+':
          this.resultado = this.numero1 + this.numero2;
          break;
        case '-':
          this.resultado = this.numero1 - this.numero2;
          break;
        case '*':
          this.resultado = this.numero1 * this.numero2;
          break;
        case '/':
          this.resultado = this.numero1 / this.numero2;
          break;
        default:
          this.resultado = 0;
      }
    },
    limpar()
    {
      this.numero1 = 0;
      this.numero2 = 0;
      this.operacao = '';
      this.resultado = 0;
    },
  },
};
</script>

<style scoped>

</style>

