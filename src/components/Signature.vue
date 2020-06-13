<template>
  <div class="page-container" contenteditable="true">
    <div class="sig-card">
    <div class="sig-container">
      <table>
      <tbody>
        <tr>
        <td rowspan="1" colspan="1" >
          <img src="../assets/dt-logo-full.png" class="dt-logo" />
        </td>
        <td rowspan="1" colspan="1">
          <div class="sig-text">
          <p class="name">{{formData.name}}</p>
          <p class="position">{{formData.position}}</p>
          <div class="divide" />
          <p class="slogan">MAKE. PROGRESS. THE FUTURE OF DIGITAL.</p>
          <p class="phone"><span v-if="formData.office">Office: {{formatPhone(formData.office)}} |</span> Mobile: {{formatPhone(formData.mobile)}}</p>
          <p class="email">{{formData.email}} | domandtom.com</p>
        </div>
        </td>
        </tr>
      </tbody>
      </table>
    </div>
    </div>
  </div>
</template>

<script>
import ClipboardJS from "clipboard";
new ClipboardJS(".btn", {
  container: document.getElementById("modal")
});
export default {
  name: "Signature",
  props: {
    formData: Object
  },
  watch: {
    formData: {
      handler(n) {
        this.formDataLocal = n;
        console.log(JSON.stringify(n));
      },
      immediate: true,
      deep: true
    }
  },
  methods: {
    formatPhone(num) {
      return num.replace(/(\d{3})(\d{3})(\d{4})/, "($1) $2 $3")
    }
  },
  computed: {},
  data: function() {
    return {
      formDataLocal: {}
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss"  scoped>
@import "../styles/signature";
</style>
