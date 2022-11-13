<template>
  <div class="home">
    <div class="navbar">
      <Navber />
    </div>
    <div class="start-water panel-a" id="panel1">
      <Home1 />
    </div>
    <div class="in-water panel panel-a panel-b" id="panel2">
      <Home2 />
    </div>
    <!-- <div class="end-water panel panel-b" id="panel3">
      <Home3 />
    </div> -->
  </div>
</template>

<script>
// @ is an alias to /src
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import TextPlugin from "gsap/TextPlugin";
import Home1 from "../components/homeComponents/Home1.vue";
import Home2 from "../components/homeComponents/Home2.vue";
// import Home3 from "../components/homeComponents/Home3.vue";
import Navber from "../components/Navbar.vue";

export default {
  name: "Home",
  components: {
    Navber,
    Home1,
    Home2,
    // Home3,
  },
  mounted() {
    gsap.registerPlugin(ScrollTrigger, TextPlugin);
    // this.changeBackground();
  },
  methods: {
    changeBackground() {
      // Dip into water
      gsap.utils.toArray(".panel-a").forEach((panel) => {
        ScrollTrigger.create({
          trigger: panel,
          start: "400 top",
          scrab: true,
          pin: true,
          pinSpacing: false,
        });
      });
      gsap.utils.toArray(".panel-b").forEach((panel) => {
        ScrollTrigger.create({
          trigger: panel,
          start: "400 top",
          scrab: true,
          pin: true,
          pinSpacing: false,
        });
      });
      // gsap.to("#panel1", () => {
      //   ScrollTrigger.create({
      //     trigger: "#panel1",
      //     start: "400 top",
      //     scrab: true,
      //     pin: true,
      //     pinSpacing: false,
      //   });
      // });
      // ScrollTrigger.create({
      //   snap: 3 / 4,
      // });
      // Float on water
      // const tl = gsap.timeline();
      // tl.from("#panel3", { yPercent: -100 });
      // ScrollTrigger.create({
      //   animation: tl,
      //   trigger: "#panel3",
      //   start: "top top",
      //   scrub: true,
      //   pin: true,
      //   anticipatePin: 1,
      // });
    },
  },
};
</script>

<style lang="scss">
@mixin pad {
  @media (max-width: 768px) {
    @content;
  }
}

@mixin phone {
  @media (max-width: 576px) {
    @content;
  }
}

.home {
  width: 100vw;
  height: 100vh;

  .navbar {
    width: 100%;
    position: fixed;
    background: none;
  }

  .panel {
    position: relative;
  }
}
</style>
