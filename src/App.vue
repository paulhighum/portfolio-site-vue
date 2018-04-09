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
          name: "Animal Dose",
          img: "../static/daf-home.png",
          logo: "../static/animal-dose-logo.png",
          description: "This is a Vue web app that displays random animal facts. Users can generate new facts, add comments, and make a donation.",
          github: "https://github.com/paulhighum/Daily-Animal-Fact-Frontend",
          live: "https://daily-animal-fact.firebaseapp.com/",
          technologies: "Vue.js, JavaScript, HTML, CSS, Stripe, Node.js, Express.js, PostgreSQL, Knex.js"
        },{
          id: 2,
          name: "Planet Wager",
          img: "../static/pw-home.png",
          logo: "../static/planet-wager-logo.png",
          description: "Planet Wager! The betting app that allows you to bet with your friends and keep track of who is losing spacebucks and who is raking them in.",
          github: "https://github.com/Space-Team/Space-Betting",
          live: "https://planetwager.herokuapp.com/main",
          technologies: "React, AntDesign React Component Library, JavaScript, HTML, CSS, Node.js, Express.js, Knex.js, PostgreSQL",
        },{
          id: 3,
          name: "Gift Genius",
          img: "../static/gg-home.png",
          logo: "../static/ggwd.png",
          description: "A Kotlin Android app that recommends gifts. Users select a number of filters in order to generate gift ideas for the relevant person and occasion.",
          github: "https://github.com/paulhighum/Gift-Genius-Kotlin-Frontend",
          demo: "https://photos.app.goo.gl/hDe0u25cOnLkEE0U2",
          technologies: "Kotlin, Android Studio, XML, PostgreSQL, Knex, Node, Express",
        },{
          id: 4,
          name: "WEREDAR",
          img: "../static/were-map.png",
          logo: "../static/were-logo-black.png",
          description: "WEREDAR allows users to track werewolves in their area. The app includes a map with werewolf location pins, a lunar cycle tracker, and  a report-a-werewolf-sighting form",
          github: "https://github.com/paulhighum/WEREDAR",
          live: "https://weredar-1.firebaseapp.com/",
          technologies: "JavaScript, Leaflet, US Navy Lunar API, HTML, CSS",
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
