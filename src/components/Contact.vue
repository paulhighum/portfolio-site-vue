<template>
  <div id="Contact">
    <h2>Send me a Message</h2>
    <form class="" action="index.html" method="post">
      <label>Name:</label>
      <input type="text" name="name" >
    </form>
  </div>
</template>
<script>
export default {
  name: "Contact",
  data() {
    return {
      emailObject {
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
</style>
