<template>
  <div id="Contact">
    <h2>Send me a Message</h2>
    <form class="email-form" action="index.html" method="post">
      <label>Name:</label>
      <input type="text" name="name" v-model="emailObject.name" />
      <label>Email:</label>
      <input type="text" name="name" v-model="emailObject.email" />
      <label>Message:</label>
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
  color: rgb(125, 173, 217);
  padding: 8vmin;
}

h2 {
  font-size: 1.75rem;
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

input, textarea {
  width: 90vmin;
  padding: 2vmin;
  font-size: 1.3rem;
  border: 2px solid rgb(125, 173, 217);
  border-radius: 5px;
  outline: none !important;
  background-color: white;
  color: rgb(125, 173, 217);
}

.contact-icons img{
  width: 64px;
  height: 64px;
}

</style>
