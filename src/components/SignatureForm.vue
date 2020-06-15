<template>
  <div class="container">
    <div class="sig-form-container">
      <label for="name">Name</label>
      <input v-model="form.name" type="text" name="name" />
      <label for="position">Position</label>
      <input v-model="form.position" type="text" name="position" />
      <label for="office">Office Phone</label>
      <input v-model="form.office" type="text" name="office" />
      <label for="other">Mobile Phone  (optional)</label>
      <input v-model="form.mobile" type="text" name="mobile" />
      <label for="email">Email</label>
      <input v-model="form.email" type="text" name="email" />
    </div>
    <div class="output">
      <p class="instructions">Copy content in container below into your Gmail Signature</p>
      <signature :formData="form" />
      <p class="instructions">Select the box, ⌘ + A (mac) / ⌃ + A (windows) copy and paste into signature field</p>
      <a href="https://support.google.com/mail/answer/8395?co=GENIE.Platform%3DDesktop&hl=en">Link to instructions</a>
    </div>
  </div>
</template>

<script>
import Signature from "./Signature";
export default {
  name: "SignatureForm",
  components: {
    Signature
  },
  props: {},
  data() {
    return {
      form: {
        name: "",
        position: "",
        office: "",
        mobile: "",
        email: ""
      }
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss"  scoped>
@import "../styles/signature-container";
</style>
