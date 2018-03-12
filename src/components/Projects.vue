<template>
  <div id="Projects">
    <h2>Selected Projects</h2>
    <div class="project-cards">
      <div class="project-card" v-for="project in projects" :key="project.id" :id="project.id" @click="openModal">
        <h3>{{project.name}}</h3>
        <img :src="project.img" alt="img">
      </div>
    </div>
    <div class="modal" v-if="projectClick">
      <div class="project-modal">
        <p @click="exitModal" class="close">&times;</p>
        <h3>{{currentProject.name}}</h3>
        <img :src="currentProject.img" alt="img">
      </div>
    </div>
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
   color: rgb(125, 173, 217);
   font-size: 1.75rem;
   padding: 0 0 4vmin 0;
}

h3 {
  color: white;
  margin: 3px 0;
  font-size: 1.5rem;
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
  margin: 40vmin auto;
  border: 1px solid rgb(136, 136, 136);
  border-radius: 5px;
  width: 80%;
  font-size: 1.5rem;
}

.project-modal h3 {
  color: black;
}

.close {
    color: #aaaaaa;
    font-size: 2rem;
    font-weight: bold;
    text-align: right;
    line-height: 1;
    padding-right: 1vmin
}

.close:hover,
.close:focus {
    color: #000;
    text-decoration: none;
    cursor: pointer;
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
    transition: background-color 1s;
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
}
</style>
