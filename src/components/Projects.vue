<template>
  <div id="Projects">
    <div class="card">
      <h2>Daily Animal Fact</h2>
      <img src="" alt="">
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
    </div>
  </div>
</template>
<script>
export default {
  name: "Projects",
}
</script>
<style scoped>
@media screen and (min-width: 686px){
  #Projects {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
  }

  .card {
    background-color: white;
    min-width: 23vw;
    min-height: 23vw;
    margin: .25vw;
    padding: .25vw;
    border: .25vw solid rgb(48, 134, 213);
    border-radius: .25vw;
  }
}

@media screen and (max-width: 686px) {
  #Projects {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
  }

  .card {
    min-width: 48vmin;
    min-height: 48vmin;
    margin: 1vmin;
    border: 2px solid rgb(48, 134, 213);
    border-radius: 5px;
  }
}

</style>
