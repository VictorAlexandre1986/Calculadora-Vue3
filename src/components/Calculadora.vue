<script setup>
  import { ref } from 'vue';


    const display = ref('');

    const appendToDisplay = (value) => {
      display.value += value;
    };

    const clearDisplay = () => {
      display.value = '';
    };

    const calculateResult = () => {
      try {
        display.value = eval(display.value);
      } catch (error) {
        display.value = 'Error';
      }
    };

   
  

</script>

<template>
  <div class="calculator">
    <input v-model="display" type="text" disabled>
    <div class="buttons">
      <button @click="appendToDisplay('1')">1</button>
      <button @click="appendToDisplay('2')">2</button>
      <button @click="appendToDisplay('3')">3</button>
      <button @click="appendToDisplay('+')">+</button>
      <button @click="appendToDisplay('4')">4</button>
      <button @click="appendToDisplay('5')">5</button>
      <button @click="appendToDisplay('6')">6</button>
      <button @click="appendToDisplay('-')">-</button>
      <button @click="appendToDisplay('7')">7</button>
      <button @click="appendToDisplay('8')">8</button>
      <button @click="appendToDisplay('9')">9</button>
      <button @click="appendToDisplay('*')">*</button>
      <button @click="clearDisplay">C</button>
      <button @click="appendToDisplay('0')">0</button>
      <button @click="calculateResult">=</button>
      <button @click="appendToDisplay('/')">/</button>
    </div>
  </div>
</template>

<style>
.calculator {
  max-width: 200px;
  margin: 0 auto;
  padding: 2rem;
  border-radius:0.3rem;
  border: 1px solid #fff;
  box-shadow: 1px 1px 5px rgba(255,255,255,0.7)
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

button {
  padding: 10px;
  margin: 5px;
  font-size: 18px;
}

button:hover {
  transform: scale(1.5rem); /* Aumenta a escala em 1 rem quando o mouse estiver sobre o botão */
}

input[type="text"]{
  height:2rem;
  border-radius:0.3rem;
  box-shadow: 1px 1px 5px rgba(255,255,255,0.7);
  margin-bottom:1.5rem;
}
</style>
