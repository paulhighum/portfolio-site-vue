<template lang="html">
  <div id="Animation">
    <p>Temp for Animation</p>
  </div>
</template>

<script>
export default {
  name: "Animation",
}
</script>

<style lang="css">
#Animation {
  background-color: rgb(157, 210, 153);
  display: flex;
  align-items: center;
  justify-content: center;
}

@media screen and (max-width: 609px) {
  #Animation {
    min-height: 80vmin;
    padding: 20vmin 0 0 0;
  }
}

@media screen and (min-width: 609px) {
  #Animation {
    min-height: 60vmin;
    padding: 8vmin 0 0 0;
  }
}
</style>
