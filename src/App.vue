<template>
  <div id="slogan">
    <div class="container" id="calculadora">
      <div class="row" id="dysplay">
        <div class="col-12 text-right">
          <div>
            <h1 class="display-1">{{ displayEquação }}</h1>
          </div>
          <div>
            <h2 class="display-4">{{ displayResultado }}</h2>
          </div>
        </div>
      </div>
      <div>
        <div class="row text-center" id="teclado">
          <button
            v-on:click="limpaDisplayEquacao(), limpaDisplayResultado()"
            type="button"
            class="col-3 btn btn-warning btn-lg"
          >
            <h1>C</h1>
          </button>
          <button
            v-on:click="concatenaDigito('(')"
            type="button"
            class="col-3 btn btn-primary btn-lg"
          >
            <h1>(</h1>
          </button>
          <button
            v-on:click="concatenaDigito(')')"
            type="button"
            class="col-3 btn btn-primary btn-lg"
          >
            <h1>)</h1>
          </button>
          <button
            v-on:click="concatenaDigito('/')"
            type="button"
            class="col-3 btn btn-primary btn-lg"
          >
            <h1>/</h1>
          </button>
        </div>
        <div class="row text-center">
          <button
            v-on:click="concatenaDigito(7)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>7</h1>
          </button>
          <button
            v-on:click="concatenaDigito(8)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>8</h1>
          </button>
          <button
            v-on:click="concatenaDigito(9)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>9</h1>
          </button>
          <button
            v-on:click="concatenaDigito('*')"
            type="button"
            class="col-3 btn btn-primary btn-lg"
          >
            <h1>X</h1>
          </button>
        </div>
        <div class="row text-center">
          <button
            v-on:click="concatenaDigito(4)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>4</h1>
          </button>
          <button
            v-on:click="concatenaDigito(5)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>5</h1>
          </button>
          <button
            v-on:click="concatenaDigito(6)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>6</h1>
          </button>
          <button
            v-on:click="concatenaDigito('-')"
            type="button"
            class="col-3 btn btn-primary btn-lg"
          >
            <h1>-</h1>
          </button>
        </div>
        <div class="row text-center">
          <button
            v-on:click="concatenaDigito(1)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>1</h1>
          </button>
          <button
            v-on:click="concatenaDigito(2)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>2</h1>
          </button>
          <button
            v-on:click="concatenaDigito(3)"
            type="button"
            class="col-3 btn btn-secondary btn-lg"
          >
            <h1>3</h1>
          </button>
          <button
            v-on:click="concatenaDigito('+')"
            type="button"
            class="col-3 btn btn-primary btn-lg"
          >
            <h1>+</h1>
          </button>
        </div>
        <div class="row text-center">
          <button
            v-on:click="concatenaDigito(0)"
            type="button"
            class="col-6 btn btn-secondary btn-lg"
          >
            <h1>0</h1>
          </button>
          <button
            v-on:click="igual()"
            type="button"
            class="col-6 btn btn-success btn-lg"
          >
            <h1>=</h1>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import "font-awesome/css/font-awesome.css";
export default {
  name: "App",
  create() {
    this.limpaDisplay();
  },
  data() {
    return {
      displayResultado: "0",
      displayEquação: "0",
      bufferNumeros: [],
    };
  },
  methods: {
    limpaDisplayEquacao() {
      this.displayEquação = "";
    },
    limpaDisplayResultado() {
      this.displayResultado = "";
    },
    concatenaDigito(numero) {
      this.displayEquação += numero;
    },
    igual() {
      console.log(this.displayEquação);
      this.displayResultado = eval(this.displayEquação);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
