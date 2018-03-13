<template lang="html">
  <div id="Header">
    <h1>Paul Highum</h1>
    <div class="menu" id="mobile-nav">
      <img src="../../static/menu.png" alt="menu" v-on:click="menuToggle = !menuToggle" />
      <transition-group name="slide-fade" tag="ul">
          <li v-if="menuToggle" key="Projects"><a href="#Projects">Projects</a></li>
          <li v-if="menuToggle" key="Resume"><a href="#Resume">Resume</a></li>
          <li v-if="menuToggle" key="About"><a href="#About">About</a></li>
          <li v-if="menuToggle" key="Contact"><a hre="#Contact">Contact</a></li>
      </transition-group>
    </div>
    <div class="menu" id="desktop-nav">
      <ul>
        <li><a href="#Projects">Projects</a></li>
        <li><a href="#Resume">Resume</a></li>
        <li><a href="#About">About</a></li>
        <li><a href="#Contact">Contact</a></li>
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
  background-color: rgb(125, 173, 217);
  color: white;
  height: 20vmin;
  position: fixed;
  width: 100vw;
}

h1 {
  margin-left: 10px;
  font-size: 2rem;
}

a {
  text-decoration: none;
  color: white;
}

@media screen and (min-width: 610px) {

  #Header {
    height: 8vmin;
  }

  #desktop-nav ul {
    display: flex;
    flex-flow: row nowrap;
  }

  #desktop-nav li {
    margin-right: 10px;
    cursor: pointer;
    font-size: 1.5rem;
  }

  #desktop-nav a {
    transition: color 1s;
    transition: background-color 1s;
    padding: 3px;
    border-radius: 5px;
  }

  #desktop-nav a:hover {
    color: rgb(125, 173, 217);
    background-color: white;
  }

  #mobile-nav {
    display: none;
  }
}

@media screen and (max-width: 610px) {
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
  }

  .slide-fade-enter-active {
    transition: all .3s ease;
  }
  .slide-fade-leave-active {
    transition: all .1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }
  .slide-fade-enter, .slide-fade-leave-to
  /* .slide-fade-leave-active below version 2.1.8 */ {
    transform: translateX(10px);
    opacity: 0;
  }

  #mobile-nav ul {
    display: flex;
    min-width: 30vmin;
    right: 17vw;
    margin-top: 4vmin;
    flex-flow: column nowrap;
    position: relative;
    background-color: rgba(125, 173, 217, .7);
    transition: render 2s;
  }

  #mobile-nav li {
    margin-bottom: 10px;
    font-size: 1.65rem;
  }
}

</style>
