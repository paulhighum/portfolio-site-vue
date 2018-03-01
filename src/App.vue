<template>
  <div id="app">
    <Header />
    <Animation />
  </div>
</template>

<script>
import Animation from "./components/Animation"
import Header from "./components/Header"

export default {
  name: 'App',
  components: {
    Animation,
    Header
  },
  data() {
    return {

    }
  },
  methods: {
    methodName() {

    }
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
  min-height: 100vh;
  width: 100%;
}

</style>
