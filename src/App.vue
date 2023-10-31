<script>
export default {
  data() {
    return {
      display: ''
    }
  },
  methods: {
    appendToDisplay(value) {
      this.display += value;
    },
    clearDisplay() {
      this.display = "";
    },
    calculateResult() {
      try {
        this.display = eval(this.display);
      } catch (error) {
        this.display = "Error";
      }
    }
  }
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <h1>Kalkulator Vueeeeee</h1>
  </header>

  <main>
    <div id="app">
        <input type="text" v-model="display" readonly>
        <br>
        <div>
            <button @click="appendToDisplay('7')">7</button>
            <button @click="appendToDisplay('8')">8</button>
            <button @click="appendToDisplay('9')">9</button>
            <button @click="appendToDisplay('+')">+</button>
        </div>
        <br>
        <div>
            <button @click="appendToDisplay('4')">4</button>
            <button @click="appendToDisplay('5')">5</button>
            <button @click="appendToDisplay('6')">6</button>
            <button @click="appendToDisplay('-')">-</button>
        </div>
        <br>
        <div>
            <button @click="appendToDisplay('1')">1</button>
            <button @click="appendToDisplay('2')">2</button>
            <button @click="appendToDisplay('3')">3</button>
            <button @click="appendToDisplay('*')">*</button>
        </div>
        <br>
        <div>
            <button @click="clearDisplay">C</button>
            <button @click="appendToDisplay('0')">0</button>
            <button @click="calculateResult">=</button>
            <button @click="appendToDisplay('/')">/</button>
        </div>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
