<template>
  <div id="app">
    <CardClock />
  </div>
</template>

<script>
import CardClock from './components/CardClock'

export default {
  name: 'app',
  components: {
    CardClock
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: -60px;
}
</style>
