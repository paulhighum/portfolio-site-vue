<template>
  <div id="Projects">
    <div class="card" v-for="project in projects" :key="project.id">
      <h2>{{project.name}}</h2>
      <img :src="project.img" alt="img">
    </div>
    <!-- <div class="card">
      <h2>Daily Animal Fact</h2>
      <img src="../../static/daf-home.png" alt="animal"/>
    </div>
    <div class="card">
      <h2>Planet Wager</h2>
      <img src="" alt="">
    </div>
    <div class="card">
      <h2>Pixel Painter</h2>
      <img src="" alt="">
    </div>
    <div class="card">
      <h2>Pixel Painter</h2>
      <img src="" alt="">
    </div> -->
  </div>
</template>
<script>
export default {
  name: "Projects",
  props: ["projects"]
}
</script>
<style scoped>
.card {
  border: 2px solid rgb(48, 134, 213);
  border-radius: 5px;
}

h2 {
  color: rgb(48, 134, 213);
  margin: 2px 0 0 0;
}

@media screen and (min-width: 749px) {
  #Projects {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
  }

  .card {
    background-color: white;
    min-width: 23vw;
    min-height: 23vw;
    margin: 0.25vw;
    padding: 0.25vw;
  }

  .card h2 {
    font-size: 1.5rem;
  }

  .card img {
    max-width: 20vw;
    max-height: 20vw;
  }
}

@media (min-width: 501px) and (max-width: 748px) {
  #Projects {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
  }

  .card {
    width: 46vmin;
    height: 46vmin;
    margin: 1vmin;
  }

  .card img {
    max-width: 40vmin;
    max-height: 40vmin;
  }
}

@media screen and (max-width: 500px) {
  .card {
    min-width: 48vmin;
    min-height: 48vmin;
    margin: 1vmin;
  }

  .card img {
    max-width: 60vmin;
    max-height: 60vmin;
  }
}
</style>
