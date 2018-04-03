<template lang="html">
  <div id="Animation">
    <img src="../../static/Welcome.svg" alt="Welcome">
  </div>
</template>

<script>
export default {
  name: "Animation",
}
</script>

<style lang="css" scoped>
#Animation {
  display: flex;
  align-items: center;
  justify-content: center;
}

img {
  min-height: 40vh;
}

@media screen and (max-width: 609px) {
  #Animation {
    min-height: 70vh;
    padding: 20vmin 0 0 0;
  }
}

@media screen and (min-width: 609px) {
  #Animation {
    min-height: 75vh;
    padding: 8vmin 0 0 0;
  }
}
</style>
