<template>
  <div id="Resume">
    <h2>Resume</h2>
    <img src="../../static/line-break.png" alt="line break" class="section-title-break">
    <p>Temp for Resume</p>
  </div>
</template>
<script>
export default {
  name: "Resume",
}
</script>
<style scoped>
#Resume {
  min-height: 70vh;
  background-color: white;
  padding: 8vmin 0 0 0;
}

h2 {
   color: black;
   font-size: 1.75rem;
   padding: 1vmin 0 0 0;
}

.section-title-break {
  min-width: 44vmin;
  max-width: 44vmin;
  padding: 0 0 1vmin 0;
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
}

</style>
