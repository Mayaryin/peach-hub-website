<template>
  <div class="hello">
    <h1 :style="headlineStyles">{{ msg }}</h1>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "headline-item",
  props: {
    msg: String,
  },
  computed: {
    headlineStyles() {
      return {
        fontSize: this.isMobile ? "32px" : "50px",
        marginTop: this.isMobile ? "20px" : "40px",
        paddingTop: this.isMobile ? "20px" : "40px",
        color: "#ff886c", // Add the color style
        fontFamily: '"Quantico", sans-serif', // Replace "Your Desired Font" with the actual font you want to use
      };
    },
    isMobile() {
      return window.innerWidth <= 768; // Adjust the breakpoint as needed
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
</style>
