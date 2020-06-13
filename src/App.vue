<template>
  <div id="app">
    <Header />
    <signature-form />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import SignatureForm from "./components/SignatureForm.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    SignatureForm,
    Footer
  }
};
</script>

<style>
#app {
  padding: 0px 20px 20px 20px;
}
</style>
