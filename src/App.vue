<template>
  <div id="app">
    <Header />
    <main>
      <Animation />
      <Projects :projects="projects"/>
      <Resume />
      <About />
      <Contact :contactIcons="contactIcons"/>
    </main>
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
          name: "Daily Animal Dose",
          img: "../static/daf-home.png",
          logo: "../static/animal-dose-logo.png",
          description: "This is a Vue web app that displays random animals facts. Users can generate new ones, add comments, and theoretically make a donation.",
          github: "https://github.com/paulhighum/Daily-Animal-Fact-Frontend",
          live: "https://daily-animal-fact.firebaseapp.com/",
          technologies: "Vue.js, JavaScript, HTML, CSS, Stripe, Node.js, Express.js, PostgreSQL, Knex.js"
        },{
          id: 2,
          name: "Planet Wager",
          img: "../static/pw-home.png",
          logo: "../static/planet-wager-logo.png",
          description: "A description",
          github: "",
          live: "",
          technologies: "",
        },{
          id: 3,
          name: "WEREdar",
          img: "../static/daf-home.png",
          logo: "../static/were-logo-black.png",
          description: "A description",
          github: "",
          live: "",
          technologies: "",
        },{
          id: 4,
          name: "Pixel Painter",
          img: "../static/pp-home.png",
          logo: "../static/pixel-painter-logo.png",
          description: "A description",
          github: "",
          live: "",
          technologies: "",
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
          img: "../static/galvanize.png",
          link: "https://talent.galvanize.com/students/1835",
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
