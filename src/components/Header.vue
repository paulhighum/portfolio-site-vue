<template lang="html">
  <div id="Header">
    <h1>Paul Highum</h1>
    <div class="menu" id="mobile-nav">
      <img src="../../static/menu.png" alt="menu" v-on:click="menuToggle = !menuToggle"/>
      <transition-group name="slide-fade" tag="ul">
          <li v-if="menuToggle" key="Projects"><a>Projects</a></li>
          <li v-if="menuToggle" key="Resume"><a>Resume</a></li>
          <li v-if="menuToggle" key="About"><a>About</a></li>
          <li v-if="menuToggle" key="Contact"><a>Contact</a></li>
      </transition-group>
    </div>
    <div class="menu" id="desktop-nav">
      <ul>
        <li><a>Projects</a></li>
        <li><a>Resume</a></li>
        <li><a>About</a></li>
        <li><a>Contact</a></li>
      </ul>
    </div>
  </div>

</template>

<script>
export default {
  name: "Header",
  props: [],
  data() {
    return {
      menuToggle: false,
    }
  },
}
</script>

<style lang="css">
#Header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(48, 134, 213);
  color: white;
  height: 20vmin;
}

h1 {
  margin-left: 10px;
  font-size: 1.75rem;
}

@media screen and (min-width: 686px) {

  #desktop-nav ul {
    display: flex;
    flex-flow: row nowrap;
  }

  #desktop-nav li {
    margin-right: 10px;
  }

  #mobile-nav {
    display: none;
  }
}

@media screen and (max-width: 686px) {
  #desktop-nav {
    display: none;
  }

  #mobile-nav {
    width: 10vmin;
    height: 10vmin;
    margin-right: 10px;
  }

  #mobile-nav img {
    height: 10vmin;
    width: 10vmin;
    background-color: rgb(48, 134, 213);
  }

  .slide-fade-enter-active {
    transition: all .3s ease;
  }
  .slide-fade-leave-active {
    transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .slide-fade-enter, .slide-fade-leave-to
  /* .slide-fade-leave-active below version 2.1.8 */ {
    transform: translateX(10px);
    opacity: 0;
  }

  #mobile-nav p {
    background-color: rgb(48, 134, 213);
  }

  #mobile-nav ul {
    display: flex;
    min-width: 30vmin;
    right: 17vw;
    margin-top: 4vmin;
    flex-flow: column nowrap;
    position: relative;
    background-color: rgba(48, 134, 213, .7);
    transition: render 2s;
  }

  #mobile-nav li {
    margin-bottom: 10px;
    font-size: 1.65rem;
  }
}

</style>
