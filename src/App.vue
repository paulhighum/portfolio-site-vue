<template>
  <div id="app">
    <Header />
    <Animation />
    <Projects :projects="projects"/>
    <Resume />
    <About />
    <Contact :contactIcons="contactIcons"/>
  </div>
</template>

<script>
import Animation from "./components/Animation"
import Header from "./components/Header"
import Projects from "./components/Projects"
import Resume  from "./components/Resume"
import About  from "./components/About"
import Contact from "./components/Contact"

export default {
  name: 'App',
  components: {
    Animation,
    Header,
    Projects,
    Resume,
    About,
    Contact,
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
          name: "Planet Wager",
          img: "../static/pw-home.png",
          description: "A description"
        },
        {
          id: 3,
          name: "Pixel Painter",
          img: "../static/pp-home.png",
          description: "A description"
        },
        {
          id: 4,
          name: "Daily Animal Fact",
          img: "../static/daf-home.png",
          description: "A description"
        }
      ],
      contactIcons: [
        {
          id: 1,
          img: "../static/github.png",
          link: "https://github.com/paulhighum",
          description: "GitHub"
        },{
          id: 2,
          img: "../static/linkedin.png",
          link: "https://www.linkedin.com/in/paul-highum/",
          description: "LinkedIn"
        },{
          id: 3,
          img: "",
          link: "",
          description: "gTalent"
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
