<template>
  <div id="app">
    <router-link :to="{ name: 'HelloWorld' }">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/coins/ethereum">Ethereum</router-link>
    <router-link to="/coins/bitcoin">Bitcoin</router-link>
    <router-link to="/coins/litecoin">Litecoin</router-link>
    <router-link to="/coins/bitcoin-cash">Bitcoin Cash</router-link>
    <router-link to="/coins/ripple">Ripple</router-link>
    <router-link to="/coins/iota">IOTA</router-link>
    <router-link to="/coins/neo">NEO</router-link>
    <router-link to="/coins/tron">TRON</router-link>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
