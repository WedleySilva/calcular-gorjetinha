<script>
export default {
  data() {
    return {
      people: "",
      count: "",
      valor_gorjeta: "",
    };
  },
  methods: {
    calcular() {
      const people = this.people;
      const count = this.count;
      const valor_gorjeta = this.valor_gorjeta;

      let valor_valor_gorjeta = 0;
      let resultado = {};

      valor_valor_gorjeta = count * (valor_gorjeta / 100);
      resultado = (count + valor_valor_gorjeta) / people;
      resultado = Math.round(resultado);
      document.getElementById("resultado").innerHTML = resultado;
    },
  },
};
</script>

<template>
  <main>
    <div class="conteudo">
      <h1>CALCULAR GORJETA</h1>
      <label>
        <p>Digite o valor da conta!</p>
        <input type="number" v-model="count" id="conta" />
      </label>

      <label>
        <p>Avalie a qualidade do atendimento!</p>
        <select oi v-model="valor_gorjeta">
          <option value="30">30% Excepcional</option>
          <option value="25">25% Muito bom</option>
          <option value="20">20% Bom</option>
          <option value="15">15% Ok</option>
          <option value="10">10% Ruim</option>
          <option value="5">5% Péssimo</option>
        </select>
      </label>

      <label
        ><p>Qual o número de pessoas dividindo a conta?</p>
        <input type="number" v-model="people" id="people" />
      </label>
      <button type="button" @click="calcular">
        Calcular R$:
        <span id="resultado"></span>
      </button>
    </div>
  </main>
</template>

<style>
* {
  font-family: Georgia, "Times New Roman", Times, serif;
}
h1 {
  color: #239d5c;
  font-family: "Archivo Black", sans-serif;
  font-size: 50px;
}
main {
  background-color: #c6f7b9;
  padding: 40px;
  border-radius: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
button {
  background-color: #cad6e0;
  border: #00ffff;
  color: #239d5c;
  height: 30px;
  width: 500px;
  border-radius: 10px;
  margin: 10px;
}
input {
  border-color: #00ffff;
  border-radius: 10px;
}
select {
  border-radius: 30px;
  border-color: #00ffff;
}
</style>
