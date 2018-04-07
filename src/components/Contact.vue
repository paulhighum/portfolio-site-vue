<template>
  <div id="Contact">
    <h2>Send Me A Message</h2>
    <img src="../../static/line-break.png" alt="line break" class="section-title-break">
    <form class="email-form" action="index.html" method="post" @submit="sendEmail">
      <label>Name</label>
      <input type="text" name="name" v-model="emailObject.name" />
      <label>Email</label>
      <input type="text" name="name" v-model="emailObject.email" />
      <label>Message</label>
      <textarea type="text" name="name" v-model="emailObject.message" rows="8" cols="100"/>
      <transition name="fade" v-if="!messageReceived">
        <input class="submit" type="submit" name="submit" value="Send Message">
      </transition>
      <transition name="fade" v-else>
        <p class="message-received" @click="messageReceived = !messageReceived">Message Sent!</p>
      </transition>
    </form>
    <div class="contact-icons">
      <div class="contact-icon" v-for="contactIcon in contactIcons" :key="contactIcon.id">
        <a :href="contactIcon.link"><img :src="contactIcon.img" alt="img"/></a>
        <p>{{contactIcon.description}}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Contact",
  props: ["contactIcons"],
  data() {
    return {
      emailObject: {
        name: "",
        email: "",
        message: "",
      },
      messageReceived: false
    }
  },
  methods: {
    sendEmail() {
      event.preventDefault()
      console.log(this.emailObject)
      fetch("https://murmuring-retreat-91093.herokuapp.com/send/", {
        method: "POST",
        headers: new Headers({ "Content-Type": "application/json"}),
        body: JSON.stringify(this.emailObject)
      })
      .then(res => res.json())
      .then(res => {
        this.messageReceived = !this.messageReceived
        return res
      })
      .catch(error => console.error("error:", error))
    }
  }
}
</script>
<style scoped>
#Contact {
  display: flex;
  flex-flow: column;
  align-items: center;
  font-size: 1.3rem;
  color: black;
  padding: 8vmin;
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

.email-form {
  display: flex;
  flex-flow: column;
  width: 90vmin;
  align-items: center;
}

label {
  padding: 1vmin 0;
}

.label-break {
  max-width: 30vmin;
}

input, textarea {
  width: 90vmin;
  padding: 2vmin;
  font-size: 1.3rem;
  border: 2px solid black;
  border-radius: 5px;
  outline: none !important;
  background-color: white;
  color: black;
}

.submit {
  color: white;
  background-color: #0277A5;
  border-color: #0277A5;
  border-radius: 5px;
  margin: 4vh 5px 0 5px;
  padding: 2vmin;
  outline: none !important;
  height: 4vh;
  font-size: 1rem;
  transition: background-color .7s;
  cursor: pointer;
  height: 7vmin;
  width: 30vmin;
}

.submit:hover {
  background-color: white;
  color: #014675;
}

.contact-icons {
  display: flex;
  flex-flow: row;
  padding-top: 2vmin;
}

.contact-icons img{
  width: 64px;
  height: 64px;
}

.contact-icon {
  padding: 2vmin;
}

.contact-icon p {
  opacity: 0;
  transition: opacity 1s;
  padding-top: 1vmin;
}

.contact-icon:hover p{
  opacity: 1;
}

.message-received {
  padding: 2vh 2vw;
  margin: 4vh 5px 0 5px;
  background-color: #0277A5;
  border-color: #0277A5;
  border-radius: 5px;
  color: white;
  cursor: pointer;
}

.fade-enter-active {
  transition: all .3s ease;
}
.fade-leave-active {
  transition: all .1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.fade-enter, .fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
@media screen and (max-width: 748px) {

  .submit {
    height: 8vh;
    width: 60vw;
  }
}

@media screen and (max-width: 610px) {
  #Contact {
    padding: 20vmin 0 0 0;
  }
}

@media screen and (max-width: 500px) {
  .section-title-break {
    min-width: 80vmin;
  }
}

</style>
