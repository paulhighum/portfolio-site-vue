<template>
  <div id="Projects">
    <h2>Selected Projects</h2>
    <img src="../assets/line-break.png" alt="line break" class="section-title-break">
    <div class="project-logos">
      <img class="project-logo" v-for="project in projects" :key="project.id" :id="project.id" @click="openModal" :src="`${publicPath}${project.logo}`" alt="logo">
    </div>
    <transition name="modal-fade">
      <div class="modal" v-if="projectClick" @click="exitModal">
        <div class="project-modal">
          <div class="modal-header-style">
            <img :src="`${publicPath}${currentProject.logo}`" alt="logo" class="modal-logo">
          </div>
          <div class="modal-body-style">
            <img :src="`${publicPath}${currentProject.img}`" alt="img" class="modal-body-img">
            <div class="modal-body-paragraphs">
              <h5>Description</h5>
              <img src="../assets/line-break.png" alt="line break">
              <p>{{currentProject.description}}</p>
              <h5>Technologies</h5>
              <img src="../assets/line-break.png" alt="line break">
              <p>{{currentProject.technologies}}</p>
              <div class="modal-footer-style">
                <button type="button" name="button" v-if="currentProject.live" @click="visitLive" >Live Site</button>
                <button type="button" name="button" v-else @click="visitDemo">View Demo</button>
                <button type="button" name="button" @click="visitGitHub" >GitHub Repo</button>
                <button class="exit-button" type="button" name="button" @click="exitModal" >Exit</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  name: "Projects",
  data() {
    return {
      projectClick: false,
      currentProject: {},
      publicPath: process.env.BASE_URL,
      projects: [
        {
          id: 1,
          name: "Animal Dose",
          img: "daf-home.png",
          logo: "animal-dose-logo.png",
          description: "This is a Vue web app that displays random animal facts. Users can generate new facts, add comments, and make a donation.",
          github: "https://github.com/paulhighum/Daily-Animal-Fact-Frontend",
          live: "https://daily-animal-fact.firebaseapp.com/",
          technologies: "Vue.js, JavaScript, HTML, CSS, Stripe, Node.js, Express.js, PostgreSQL, Knex.js"
        },{
          id: 2,
          name: "Planet Wager",
          img: "pw-home.png",
          logo: "planet-wager-logo.png",
          description: "Planet Wager! The betting app that allows you to bet with your friends and keep track of who is losing spacebucks and who is raking them in.",
          github: "https://github.com/Space-Team/Space-Betting",
          live: "https://planetwager.herokuapp.com/main",
          technologies: "React, AntDesign React Component Library, JavaScript, HTML, CSS, Node.js, Express.js, Knex.js, PostgreSQL",
        },{
          id: 3,
          name: "Gift Genius",
          img: "gg-home.png",
          logo: "ggwd.png",
          description: "A Kotlin Android app that recommends gifts. Users select a number of filters in order to generate gift ideas for the relevant person and occasion.",
          github: "https://github.com/paulhighum/Gift-Genius-Kotlin-Frontend",
          demo: "https://photos.app.goo.gl/7B04Yr6K9kQblsWH2",
          technologies: "Kotlin, Android Studio, XML, PostgreSQL, Knex.js, Node.js, Express.js",
        },{
          id: 4,
          name: "WEREDAR",
          img: "were-map.png",
          logo: "were-logo-black.png",
          description: "WEREDAR allows users to track werewolves in their area. The app includes a map with werewolf location pins, a lunar cycle tracker, and  a report-a-werewolf-sighting form",
          github: "https://github.com/paulhighum/WEREDAR",
          live: "https://weredar-1.firebaseapp.com/",
          technologies: "JavaScript, Leaflet, US Navy Lunar API, HTML, CSS",
        }
      ]
    }
  },
  methods: {
    openModal(e) {
      this.currentProject = this.projects.filter(project => {
        return project.id === Number(e.target.id)
      })[0]
      this.projectClick = true
    },
    exitModal(e) {
      e.stopPropagation()
      if(e.target.className === "exit-button" || e.target.className === "modal"){
        this.projectClick = !this.projectClick
      }

    },
    visitLive(){
      window.open(this.currentProject.live, '_blank')
    },
    visitGitHub(){
      window.open(this.currentProject.github, '_blank')
    },
    visitDemo(){
      window.open(this.currentProject.demo, '_blank')
    }
  }
}
</script>
<style scoped>

h2 {
   color: black;
   font-size: 2.25rem;
   padding: 1vmin 0 0 0;
   font-weight: bold;
}

.section-title-break {
  max-width: 44vmin;
}

.project-logo {
  min-width: 40vw;
  padding: 2vmin 4vw;
  cursor: pointer;
}

.project-logo:nth-child(2) {
  padding: 0 4vw;
}

.modal-fade-enter-active, .modal-fade-leave-active {
  transition: opacity .65s;
}
.modal-fade-enter, .modal-fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}

.modal {
    display: block;
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.4);
}

.project-modal {
  background-color: rgb(254, 254, 254);
  margin: 20vmin auto;
  border: 1px solid rgb(136, 136, 136);
  border-radius: 5px;
  width: 90vmin;
  height: 75%;
  font-size: 1.5rem;
  padding: 1vmin;
}

.project-modal h4 {
  color: black;
  padding: 10px 0 0 0;
  font-size: 1.75rem;
}

.modal-header-style {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}

.modal-header-style img {
  max-width: 42vmin;
  max-height: 10vh;
}

.modal-body-style {
  display: flex;
  flex-flow: row;
  justify-content: space-between;
  height: 80%;
}

.modal-body-style img {
  max-height: 60vmin;
  max-width: 42vmin;
  align-self: center;
}

.modal-body-img {
  padding: 2vmin 0 0 2vmin;
}

.modal-body-style h5 {
  padding: 20px 0 0 0;
}

.modal-body-style p {
  padding: 0 2.5vmin;
}

.modal-footer-style {
  padding: 3vmin 0 2vmin 0;
}

.modal-footer-style button{
  height: 4.5vmin;
  width: 14vmin;
  background-color: #0277A5;
  border-radius: 5px;
  border: 1px solid #0277A5;
  font-size: .85rem;
  color: white;
  cursor: pointer;
  outline: none !important;
  transition: background-color .5s;
}

.modal-footer-style button:hover {
  color: #014675;
  background-color: white;
}

@media screen and (min-width: 1150px){
  .project-logo {
    min-width: 30vw;
  }
}

@media screen and (min-width: 749px) {

  img {
    max-width: 20vw;
    max-height: 20vw;
  }

}

@media screen and (max-width: 647px) {
  #Projects {
    padding: 20vmin 0 0 0;
  }
}

@media screen and (min-width: 648px) {
  #Projects {
    padding: 10vmin 0 0 0;
  }
}

@media (min-width: 501px) and (max-width: 748px) {

  img {
    max-width: 60vmin;
    max-height: 60vmin;
  }

  .section-title-break {
    min-width: 60vmin;
  }

  .project-logo {
    padding: 4vh 0;
  }

  .project-logo:nth-child(2) {
    padding: 4vh 0;
  }

  .modal-body-style {
    display: flex;
    flex-flow: column;
    overflow: scroll;
  }

  .modal-footer-style button{
    height: 4.5vw;
    width: 14vw;
    background-color: #0277A5;
    border-radius: 5px;
    border: 1px solid #0277A5;
    font-size: .85rem;
    color: white;
    outline: none !important;
  }
}

@media screen and (max-width: 500px) {
  img {
    max-width: 60vmin;
    max-height: 60vmin;
  }

  .section-title-break {
    min-width: 80vmin;
  }

  .project-logo {
    padding: 4vh 0;
  }

  .project-logo:nth-child(2) {
    padding: 4vh 0;
  }

  .modal-header-style img {
    max-width: 80vmin;
    max-height: 20vh;
  }

  .modal-body-style {
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    min-width: 80%;
    overflow: scroll;
  }

  .modal-body-style img{
    max-height: 100vmin;
    min-width: 64vmin;
  }

  .modal-body-img {
    padding: 2vmin 0 0 0;
  }

  .modal-footer-style button{
    height: 10vmin;
    width: 26vmin;
    background-color: #0277A5;
    border-radius: 5px;
    border: 1px solid #0277A5;
    font-size: .85rem;
    color: white;
    outline: none !important;
  }
}

@media (min-width: 700px) and (max-height: 699px) {
  .modal-body-style {
    display: flex;
    flex-flow: column;
    overflow: scroll;
  }

  .modal-footer-style button{
    height: 4.5vw;
    width: 12vw;
    background-color: #0277A5;
    border-radius: 5px;
    border: 1px solid #0277A5;
    font-size: .85rem;
    color: white;
    outline: none !important;
    margin: 1vmin;
  }
}
</style>
