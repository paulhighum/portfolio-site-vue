<template>
  <div id="About">
    <div class="about-style">
      <h2>About</h2>
      <p> I am a Full Stack Developer who gets a thrill from writing successful logic in any programming language. I enjoy learning about new technologies, pairing on code, and participating in hackathons.
          As a student at Galvanize I developed skills on both the frontend and backend, and have an interest in working in either area. I have learned a couple of languages and frameworks and would be eager to pick up new ones.
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
  width: 90vmin;
  padding: 2vmin;
  border: 2px solid rgb(125, 173, 217);
  border-radius: 5px;
  background-color: rgb(125, 173, 217)
}

h2 {
  font-size: 1.75rem;
  padding: 2vmin;
}

</style>
