<template>
  <div class="home2">
    <img src="../../assets/images/background/background2.svg" alt="">
  </div>
</template>

<script>
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import TextPlugin from "gsap/TextPlugin";
export default {
  mounted() {
    gsap.registerPlugin(ScrollTrigger, TextPlugin);
    this.scrollBackground();
  },
  methods: {
    scrollBackground() {
      // gsap.set('.home2', { position: 'fixed', width: 7900, height: 5600, transformOrigin: '0 0' });
      // gsap.to('.home2', { duration: 1, opacity: 1, ease: 'power2.inOut', delay: 0.3 });
      // gsap.timeline({ scrollTrigger: { trigger: '.home', start: 'left bottom', end: 'right bottom', scrub: 1 } });
      // .to('#c', { motionPath: '#p', immediateRender: true, ease: 'none' }, 0)
      // .from('#p', { drawSVG: '0 0', ease: 'none' }, 0)
      // window.onload = window.onresize = () => { gsap.set('#container', { left: innerWidth / 2, top: innerHeight / 2 }); };
    }
  },
};
</script>

<style lang="scss">
.home2 {
  // width: 5000px;
  // height: 100vh;
  background-color: #fff;

  // background-position: 0 0;
  img {
    height: 200vh;
    overflow: scroll;
    position: absolute;
    left: 0%;
  }
}
</style>
