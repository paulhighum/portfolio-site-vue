<template lang="html">
  <div id="Header">
    <h1>Paul Highum</h1>
    <div class="menu" id="mobile-nav">
      <img src="../../static/menu.png" alt="menu" v-on:click="menuToggle = !menuToggle" />
      <transition-group name="slide-fade" tag="ul">
          <li v-if="menuToggle" key="Projects"><a href="#Projects" @click="menuToggle = !menuToggle" v-smooth-scroll>Projects</a></li>
          <li v-if="menuToggle" key="Resume"><a href="#Resume" @click="menuToggle = !menuToggle" v-smooth-scroll>Resume</a></li>
          <li v-if="menuToggle" key="About"><a href="#About" @click="menuToggle = !menuToggle" v-smooth-scroll>About</a></li>
          <li v-if="menuToggle" key="Contact"><a href="#Contact" @click="menuToggle = !menuToggle" v-smooth-scroll>Contact</a></li>
      </transition-group>
    </div>
    <div class="menu" id="desktop-nav">
      <ul>
        <li><a href="#Projects" v-smooth-scroll>Projects</a></li>
        <li><a href="#Resume" v-smooth-scroll>Resume</a></li>
        <li><a href="#About" v-smooth-scroll>About</a></li>
        <li><a href="#Contact" v-smooth-scroll>Contact</a></li>
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
  background-color: #0277A5;
  color: white;
  height: 20vmin;
  position: fixed;
  width: 100vw;
}

h1 {
  margin-left: 10px;
  font-size: 3rem;
  font-weight: bold;
  padding: 2px;
}

a {
  text-decoration: none;
  color: white;
  font-weight: bold;
}

@media screen and (min-width: 648px) {

  #Header {
    height: 10vmin;
  }

  #desktop-nav ul {
    display: flex;
    flex-flow: row nowrap;
  }

  #desktop-nav li {
    margin-right: 10px;
    cursor: pointer;
    font-size: 1.85rem;
  }

  #desktop-nav a {
    transition: background-color .7s;
    padding: 3px;
    border-radius: 5px;
  }

  #desktop-nav a:hover {
    color: #014675;
    background-color: white;
  }

  #mobile-nav {
    display: none;
  }
}

@media screen and (max-width: 647px) {
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
    background-color: rgba(2, 119, 165, .7);
    transition: render 2s;
  }

  #mobile-nav li {
    margin-bottom: 10px;
    font-size: 1.65rem;
  }
}

</style>
