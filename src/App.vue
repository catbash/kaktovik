<script setup>
  import { ref } from 'vue';
  import KaktovikImg from "./components/Kaktovik.vue";
  
  const base10 = ref('');
  const base20 = ref('');
  const alert = ref('');

  function ten2twenty () {
    base20.value = '';
    if (base10.value === '') return;
    const intRegex = /^\d+$/;
    if (intRegex.test(base10.value)) {
      base20.value = Number(base10.value).toString(20);
    } else {
      base10.value = '';
      alert.value = 'Please enter a whole number!';
    }
  }

  function reset () {
    alert.value = '';
  }

</script>

<template>
  <div id="app">
    <div id="app-contents">
      <form @submit.prevent="ten2twenty">
        <input type="text" @click="reset" v-model="base10" placeholder="Enter a number..." />
        <button>Kaktovik Iñupiaq</button>
      </form>
      <div class="alert">{{ alert }}</div>
      <div class="kaktovik">
        <div class="kaktovik-num" v-for="char in base20.split('')" :key="char.index">
          <KaktovikImg :number="char" />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
  :root, * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-family: sans-serif;
    color: #fff;
  }

  html, body {
    background: #111;
  }

  button {
    cursor: pointer;
    margin-top: 0.5rem;
    background: transparent;
    outline: 1px solid #fff;
    border: none;
    border-radius: 3px;
    padding: 0.15rem 0.5rem;
    opacity: 0.5;
  }

  button:hover {
    opacity: 1;
    background: #fff;
    color: #111;
  }

  h1 {
    margin-bottom: 1rem;
  }

  input, input:focus {
    display: block;
    padding: 0.5rem;
    border-radius: 3px;
    margin: 0 auto;
    background: #111;
    border: 1px solid #fff;
    outline: none;
    opacity: 0.5;
    text-align: center;
  }

  input:hover {
    opacity: 1;
  }

  input:focus {
    background: #222;
  }

  .alert {
    color: red;
    font-size: 0.8rem;
    margin-top: 0.5rem;
  }

  #app {
    height: 100vh;
    width: 100vw;
    display: grid;
    align-items: center;
  }

  #app-contents {
    text-align: center;
    margin: 0 auto;
    min-height: 235px;
    padding: 1rem;
  }

  .kaktovik {
    text-align: center;
  }

  .kaktovik-num {
    display: inline-block;
    filter: invert();
  }
</style>
