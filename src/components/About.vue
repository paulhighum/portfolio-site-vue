<template>
  <div id="About">
    <div class="about-style">
      <h2>About:</h2>
      <p> Hey guys, I'm Paul.
          I was born in Marin County California, but then I moved to Denver when I was three months old.
          I lived in Denver until attending UCLA, where I graduated with a history degree.
          After that I moved home with the intention of finishing my novel, but instead I quickly became an embarassing, basement-living, computer-gaming cliche.
          So I got a job at DISH and took the intro to JS night course here.
        </p>
        <br>
        <p>
          By night I enjoy sleeping, by day I enjoy traveling, reading, writing, videogames, skiing, and eating.
        </p>
    </div>
  </div>
</template>
<script>
export default {
  name: "About",
}
</script>
<style scoped>
#About {
  width: 100vw;
  display: flex;
  justify-content: center;
  padding: 8vmin 0;
  color: white;
  font-size: 1.3rem;
}

.about-style {
  width: 70vw;
  padding: 2vmin;
  border: 2px solid rgb(48, 134, 213);
  border-radius: 5px;
  background-color: rgb(48, 134, 213)
}

h2 {
  font-size: 1.75rem;
  padding: 2vmin;
}

</style>
