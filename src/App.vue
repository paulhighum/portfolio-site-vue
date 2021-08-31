<template>
  <Header />
  <main>
      <Animation />
      <Projects />
      <Resume />
      <About />
      <Contact />
    </main>
</template>

<script>
import Header from './components/Header.vue'
import Animation from './components/Animation.vue'
import Projects from './components/Projects.vue'
import Resume  from './components/Resume.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'


export default {
  name: 'App',
  components: {
    Header,
    Animation,
    Projects,
    Resume,
    About,
    Contact
  },
  methods: {
    methodName() {

    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Open+Sans+Condensed:300');

#app {
  font-family: 'Open Sans Condensed', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  min-height: 100vh;
  width: 100%;
}

</style>
