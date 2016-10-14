<template>
  <div id="app">
    <h1>
      <span>{{ adjective }}</span>
      <span>{{ cocktail }}</span>
    </h1>
    <button @click="funk()">Get Funkier!</button>
  </div>
</template>

<script>
import adjectives from 'src/adjectives.json'
import cocktails from 'src/cocktails.json'
// eslint-disable-next-line
String.prototype.capitalize = function () {
  return this.charAt(0).toUpperCase() + this.slice(1)
}

function choose (arr) {
  const len = arr.length
  const index = Math.floor(Math.random() * len)
  return arr[index].capitalize()
}

export default {
  data () {
    return {
      adjective: choose(adjectives),
      cocktail: choose(cocktails)
    }
  },
  methods: {
    funk () {
      this.adjective = choose(adjectives)
      this.cocktail = choose(cocktails)
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

button {
  border: 3px solid #2c3e50;
  background-color: transparent;
  padding: 0.5rem;
  font: inherit;
  color: inherit;
  font-weight: bold;
  cursor: pointer;
}

</style>
