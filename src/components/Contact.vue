<template>
  <div id="Contact">
    <h2>Send Me A Message</h2>
    <img src="../assets/line-break.png" alt="line break" class="section-title-break">
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
        <p class="message-received" @click="messageReceived = !messageReceived">{{returnMessage}}</p>
      </transition>
    </form>
    <div class="contact-icons">
      <div class="contact-icon" v-for="contactIcon in contactIcons" :key="contactIcon.id" @click="visitSite(contactIcon.link)" >
        <img :src="contactIcon.img" alt="img"/>
        <p>{{contactIcon.description}}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Contact",
  data() {
    return {
      emailObject: {
        name: "",
        email: "",
        message: "",
      },
      messageReceived: false,
      returnMessage: "Message Sent!",
      contactIcons: [
        {
          id: 1,
          img: "/img/github.png",
          link: "https://github.com/paulhighum",
          description: "GitHub"
        },{
          id: 2,
          img: "/img/linkedin.png",
          link: "https://www.linkedin.com/in/paul-highum/",
          description: "LinkedIn"
        },{
          id: 3,
          img: "/img/galvanize.png",
          link: "https://talent.galvanize.com/students/1835",
          description: "gTalent"
        }
      ]
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
        this.emailObject = {
          name: "",
          email: "",
          message: "",
        }
        return res
      })
      .catch(error => console.error("error:", error))
    },
    visitSite(link) {
      window.open(link, "_blank")
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
  padding: 10vmin;
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

.email-form {
  display: flex;
  flex-flow: column;
  width: 90vmin;
  align-items: center;
}

label {
  padding: 1vmin 0;
  font-size: 1.6rem;
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
  padding: 1vmin;
  outline: none !important;
  height: 4vh;
  font-size: 1.4rem;
  transition: background-color .7s;
  cursor: pointer;
  height: 7vmin;
  width: 30vmin;
  font-family: 'Open Sans Condensed', sans-serif;
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
  cursor: pointer;
}

.contact-icon p {
  opacity: 0;
  transition: opacity 1s;
  padding-top: 1vmin;
  color: #014675;
}

.contact-icon:hover p{
  opacity: 1;
}

.message-received {
  padding: 2vh 2vw;
  margin: 4vh 5px 0 5px;
  background-color: #0277A5;
  border: 1px solid #0277A5;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  font-size: 1.4rem;
}

.message-received:hover {
  background-color: white;
  color: #014675;
  border-color: #0277A5;
  border-radius: 5px;
}

.message-received:hover p::after{
  content: "Different";
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
