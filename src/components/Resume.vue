<template>
  <div id="Resume">
    <h2>Resume</h2>
    <img src="../../static/line-break.png" alt="line break" class="section-title-break">
    <div class="resume-container">
      <img id="resume-png" src="../../static/resume.png" alt="resume">
      <div class="resume-highlights">
        <h3>Highlights</h3>
        <img src="../../static/line-break.png" alt="line break" class="small-section-title-break">
        <ul class="highlights-list">
          <li>Galvanize Web Development Immersive Grad</li>
          <li>Technical Skill Highlights: HTML5, CSS3, JavaScript, React, Vue, Android Studio, and Kotlin</li>
          <li>Project Development Using Agile Methodologies</li>
          <li>Graduated Summa Cum Laude From UCLA In Three Years</li>
          <li>Experience Working In A Fast Paced Professional Environment At DISH Network</li>
        </ul>
        <button type="button" name="button" @click="visitResume">View Resume PDF</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Resume",
  methods: {
    visitResume() {
      window.location.href = "https://drive.google.com/file/d/1neQbFfSl7Qt1HwzBDqKEY-Inz80tcBAk/view?usp=sharing"
    }
  }
}
</script>
<style scoped>
#Resume {
  min-height: 70vh;
  background-color: white;
  padding: 10vmin 0 0 0;
  display: flex;
  flex-flow: column;
  align-items: center;
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

#resume-png {
  max-width: 40vw;
  padding: 0 1vw 0 0;
}

.resume-container {
  display: flex;
  align-items: flex-start;
}

.resume-highlights {
  display: flex;
  flex-flow: column;
  align-items: center;
  padding: 0 0 0 1vw;
  width: 40vw;
}

h3 {
  color: black;
  font-size: 1.85rem;
  font-weight: bold;
  /* padding: 1vmin 0 0 0; */
}

.small-section-title-break {
  min-width: 36vmin;
  max-width: 36vmin;
  padding: 0 0 1vmin 0;
}

ul  {
  font-size: 1.5rem;
}

li {
  text-align: left;
  padding: 2vh 0 0 0;
  line-height: 1.2;
  margin-left: 3vw;
  color: black;
}

li:before{
   content: "";
   display: inline-block;
   height: 16px;
   width: 16px;
   background-image: url("../../static/line-break-bullet.png");
   background-size: cover;
   background-repeat: no-repeat;
   margin-right: .5vw;
}

button {
  color: white;
  background-color: #0277A5;
  border-color: #0277A5;
  border-radius: 5px;
  margin: 4vh 5px 0 5px;
  outline: none !important;
  height: 4vh;
  font-size: 1.4rem;
  transition: background-color .7s;
  cursor: pointer;
  height: 7vmin;
  width: 30vmin;
  font-family: 'Open Sans Condensed', sans-serif;
}

button:hover {
  background-color: white;
  color: #014675;
}

@media screen and (max-width: 748px) {
  .resume-container {
    display: flex;
    flex-flow: column;
    align-items: center;
  }

  #resume-png {
    max-width: 80vw;
    padding: 0 1vw 0 0;
  }

  .resume-highlights {
    width: 80vw;
  }

  .resume-highlights h3 {
    padding: 3vh 0 0 0;
  }

  button {
    height: 8vh;
    width: 60vw;
  }
}

@media screen and (max-width: 610px) {
  #Resume {
    padding: 20vmin 0 0 0;
  }
}

@media screen and (max-width: 500px) {
  .section-title-break {
    min-width: 80vmin;
  }

  .small-section-title-break {
    min-width: 70vmin;
  }
}

</style>
