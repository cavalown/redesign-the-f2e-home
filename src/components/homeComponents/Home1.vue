<template>
  <div class="home1">
    <Navbar />
    <div class="title">
      <h1>互動網頁設計</h1>
      <ul>
        <li>UI Design</li>
        <li>FrontEnd</li>
      </ul>
      <p>滾動開始</p>
      <div class="hint">
        <img id="hint-arrow" src="../../assets/images/elements/arrow-down.png" alt="請向下滾動" />
      </div>
    </div>
    <div class="submarine-float">
      <img class="submarine" id="submarine" src="../../assets/images/elements/submarine1.png" alt="潛水艇" />
      <img class="water-surface" src="../../assets/images/elements/water-surface1.png" alt="潛水艇接處水面" />
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import TextPlugin from "gsap/TextPlugin";
import Navbar from "../Navbar.vue";
export default {
  components: {
    Navbar,
  },
  mounted() {
    gsap.registerPlugin(ScrollTrigger, TextPlugin);
    this.arrowRun();
    this.submarineUpAndDown();
  },
  methods: {
    arrowRun() {
      gsap.to("#hint-arrow", {
        y: 30,
        duration: 1,
        repeat: -1,
      });
    },
    submarineUpAndDown() {
      gsap.to("#submarine", {
        y: 20,
        duration: 1.2,
        repeat: -1,
        yoyo: true,
      });
    },
    birdsFly() { },
  },
};
</script>

<style lang="scss">
.home1 {
  height: 981px;
  background-image: url("../../assets/images/background/background1.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: absolute;

  .title {
    h1 {
      margin-bottom: 35px;
      color: #2a99d9;
      font-size: 36px;
      font-weight: 400;
    }

    ul {
      width: 327px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      color: #2a99d9;
      font-size: 24px;
      font-weight: 400;
    }

    p {
      margin-top: 29px;
      color: #2a99d9;
      font-size: 14px;
      font-weight: 700;
    }

    .hint {
      margin: 0 auto;
      margin-top: 15px;
      width: 34px;
      height: 50px;
      border-radius: 80px;
      background-color: #fff;
    }
  }

  .submarine-float {
    .submarine {
      position: absolute;
      top: 530px;
      left: 255px;
      height: 218px;
      width: 264px;
    }

    .water-surface {
      position: absolute;
      top: 740px;
      left: 255px;
    }
  }
}
</style>
