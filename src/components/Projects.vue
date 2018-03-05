<template>
  <div id="Projects">
    <h2>Selected Projects</h2>
    <div class="project-cards">
      <div class="project-card" v-for="project in projects" :key="project.id">
        <h3>{{project.name}}</h3>
        <img :src="project.img" alt="img">
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Projects",
  props: ["projects"]
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
