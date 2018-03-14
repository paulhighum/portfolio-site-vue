<template>
  <div id="Contact">
    <h2>Send Me A Message</h2>
    <img src="../../static/line-break.png" alt="line break" class="section-title-break">
    <form class="email-form" action="index.html" method="post">
      <label>Name</label>
      <input type="text" name="name" v-model="emailObject.name" />
      <label>Email</label>
      <input type="text" name="name" v-model="emailObject.email" />
      <label>Message</label>
      <textarea type="text" name="name" v-model="emailObject.message" rows="8" cols="100"/>
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
      }
    }
  },
  methods: {
    sendEmail() {
      console.log(this.emailObject, "sent")
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

@media screen and (max-width: 500px) {
  .section-title-break {
    min-width: 80vmin;
  }
}

</style>
