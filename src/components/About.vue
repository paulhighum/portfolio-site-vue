<template>
  <div id="About">
    <h2>About Me</h2>
    <img src="../../static/line-break.png" alt="line break" class="section-title-break">
    <div class="about-style">
      <p> I am a Full Stack Developer who gets a thrill from writing successful logic in any programming language. I enjoy learning new technologies, collaborating with my teammates, and mentoring Junior Developers.
          I have curated skills in project management, in people management, and throughout the development lifecycle that I would be excited to bring to your team.
        </p>
        <br>
        <p>
          I have lived in Denver most of my life, apart from a brief sojourn in LA for college. By night I enjoy sleeping, by day I enjoy traveling, reading, writing, videogames, skiing, and eating.
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
  flex-flow: column;
  justify-content: center;
  align-items: center;
  padding: 10vmin 0;
  color: white;
  font-size: 1.3rem;
}

.about-style {
  width: 90vmin;
  padding: 2vmin;
  border: 2px solid #0277A5;
  border-radius: 5px;
  background-color: #0277A5
}

h2 {
   color: black;
   font-size: 2.25rem;
   padding: 1vmin 0 0 0;
   font-weight: bold;
}

.section-title-break {
  min-width: 44vmin;
  max-width: 44vmin;
  padding: 0 0 1vmin 0;
}

p {
  font-size: 1.6rem;
}

@media screen and (max-width: 610px) {
  #About {
    padding: 20vmin 0 0 0;
  }
}

@media screen and (max-width: 500px) {
  .section-title-break {
    min-width: 80vmin;
  }
}

</style>
