<template>
  <div id="Projects">
    <h2>Selected Projects</h2>
    <img src="../../static/line-break.png" alt="line break" class="section-title-break">
    <div class="project-cards">
      <div class="project-card" v-for="project in projects" :key="project.id" :id="project.id" @click="openModal">
        <h3>{{project.name}}</h3>
        <img :src="project.img" alt="img">
      </div>
    </div>
    <transition name="modal-fade">
      <div class="modal" v-if="projectClick" >
        <div class="project-modal">
          <div class="modal-header-style">
            <h4>{{currentProject.name}}</h4>
            <img src="../../static/line-break.png" alt="line break">
          </div>
          <div class="modal-body-style">
            <img :src="currentProject.img" alt="img">
            <div class="modal-body-paragraphs">
              <h5>Description</h5>
              <img src="../../static/line-break.png" alt="line break">
              <p>{{currentProject.description}}</p>
              <h5>Technologies</h5>
              <img src="../../static/line-break.png" alt="line break">
              <p>{{currentProject.technologies}}</p>
              <div class="modal-footer-style">
                <button type="button" name="button" @click="visitLive" >Live Site</button>
                <button type="button" name="button" @click="visitGitHub" >GitHub Repo</button>
                <button type="button" name="button" @click="exitModal" >Exit</button>
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
  props: ["projects"],
  data() {
    return {
      projectClick: false,
      currentProject: {},
    }
  },
  methods: {
    openModal() {
      this.currentProject = this.projects.filter(project => {
        return project.id === Number(event.target.id)
      })[0]
      this.projectClick = true
    },
    exitModal() {
      this.projectClick = false
    },
    visitLive(){
      window.location.href = this.currentProject.live
    },
    visitGitHub(){
      window.location.href = this.currentProject.github
    }
  }
}
</script>
<style scoped>
.project-card {
  border: 2px solid rgb(125, 173, 217);
  border-radius: 5px;
  background-color: rgb(125, 173, 217)
}

h2 {
   color: black;
   font-size: 1.75rem;
   padding: 1vmin 0 0 0;
}

.section-title-break {
  min-width: 44vmin;
}

h3 {
  color: white;
  margin: 3px 0;
  font-size: 1.65rem;
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
  margin: 25vmin auto;
  border: 1px solid rgb(136, 136, 136);
  border-radius: 5px;
  width: 90vmin;
  height: 70%;
  font-size: 1.5rem;
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
  min-width: 42vmin
}

.modal-body-style {
  display: flex;
  flex-flow: row;
  justify-content: space-between;
  height: 80%;
}

.modal-body-style img {
  max-height: 60vmin;
  min-width: 42vmin;
  align-self: center;
}

.modal-body-style h5 {
  padding: 20px 0 0 0;
}

.modal-body-style p {
  padding: 0 2.5vmin;
}

.modal-footer-style {
  padding: 5vmin 0 2vmin 0;
}

.modal-footer-style button{
  height: 4.5vmin;
  width: 14vmin;
  background-color: rgb(125, 173, 217);
  border-radius: 5px;
  border: 1px solid rgb(125, 173, 217);
  font-size: .85rem;
  color: white;
  cursor: pointer;
  outline: none !important;
  transition: background-color .5s;
}

.modal-footer-style button:hover {
  color: rgb(125, 173, 217);
  background-color: white;
}

@media screen and (min-width: 749px) {
  #Projects {
    padding: 8vmin 0 0 0;
  }

  .project-cards {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
  }

  .project-card {
    min-width: 23vw;
    min-height: 23vw;
    margin: 0.25vw;
    padding: 0.25vw;
    display: flex;
    flex-flow: column;
    align-items: center;
    transition: background-color .5s;
  }

  .project-card:hover {
    background-color: white;
    cursor: pointer;
  }

  .project-card:hover h3 {
    color: rgb(125, 173, 217);
  }

  h3 {
    transition: color 1s;
  }

  img {
    max-width: 20vw;
    max-height: 20vw;
  }
}

@media (min-width: 501px) and (max-width: 748px) {
  .project-cards {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
  }

  .project-card {
    width: 46vmin;
    height: 46vmin;
    margin: 1vmin;
  }

  img {
    max-width: 40vmin;
    max-height: 40vmin;
  }
}

@media screen and (max-width: 500px) {
  .project-card {
    min-width: 48vmin;
    min-height: 48vmin;
    margin: 1vmin;
  }

  img {
    max-width: 60vmin;
    max-height: 60vmin;
  }

  .modal-body-style {
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    min-width: 80%;
    overflow: scroll;
  }

  .modal-body-style img{
    max-height: 80vmin;
    min-width: 64vmin;
  }

  .modal-footer-style button{
    height: 10vmin;
    width: 26vmin;
    background-color: rgb(125, 173, 217);
    border-radius: 5px;
    border: 1px solid rgb(125, 173, 217);
    font-size: .85rem;
    color: white;
    outline: none !important;
  }

}
</style>
