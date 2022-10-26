<template>
  <div class="home">
    <Home1 />
    <Home2 />
    <Home3 />
    <Home4 />
    <Home5 />
    <Home6 />
    <Home7 />
    <Home8 />
    <Home9 />
    <!-- <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import TextPlugin from "gsap/TextPlugin";
import Home1 from "../components/homeComponents/Home1.vue";
import Home2 from "../components/homeComponents/Home2.vue";
import Home3 from "../components/homeComponents/Home3.vue";
import Home4 from "../components/homeComponents/Home4.vue";
import Home5 from "../components/homeComponents/Home5.vue";
import Home6 from "../components/homeComponents/Home6.vue";
import Home7 from "../components/homeComponents/Home7.vue";
import Home8 from "../components/homeComponents/Home8.vue";
import Home9 from "../components/homeComponents/Home9.vue";

export default {
  name: "Home",
  components: {
    Home1,
    Home2,
    Home3,
    Home4,
    Home5,
    Home6,
    Home7,
    Home8,
    Home9,
  },
  created() {
    gsap.registerPlugin(ScrollTrigger, TextPlugin);
  },
};
</script>

<style lang="scss">

</style>
