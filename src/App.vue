<template>
  <div id="app">
    <Header />
    <Animation />
    <Projects :projects="projects"/>
  </div>
</template>

<script>
import Animation from "./components/Animation"
import Header from "./components/Header"
import Projects from "./components/Projects"

export default {
  name: 'App',
  components: {
    Animation,
    Header,
    Projects,
  },
  data() {
    return {
      projects: [
        {
          id: 1,
          name: "Daily Animal Fact",
          img: "../static/daf-home.png",
          description: "A description"
        },
        {
          id: 2,
          name: "Daily Animal Fact",
          img: "../static/daf-home.png",
          description: "A description"
        },
        {
          id: 3,
          name: "Daily Animal Fact",
          img: "../static/daf-home.png",
          description: "A description"
        },
        {
          id: 4,
          name: "Daily Animal Fact",
          img: "../static/daf-home.png",
          description: "A description"
        }
      ]
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
