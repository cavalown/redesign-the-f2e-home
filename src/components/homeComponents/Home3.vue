<template>
  <div class="home3">
    <h1>鑽石級贊助商</h1>
    <div class="submarine-float">
      <img
        class="submarine"
        id="submarine"
        src="../../assets/images/elements/submarine1.png"
        alt="潛水艇"
      />
      <img
        class="water-surface"
        src="../../assets/images/elements/water-surface2.png"
        alt="潛水艇接處水面"
      />
    </div>
    <div class="sponsors">
      <div class="ice">
        <img
          id="blockstudio"
          src="../../assets/images/elements/blockstudio_logo.png"
          alt="板塊設計"
        />
        <img
          class="ice-water-surface"
          src="../../assets/images/elements/blockstudio-water-surface.png"
          alt="水面"
        />
      </div>
      <div class="ice">
        <img
          id="kdan"
          src="../../assets/images/elements/kdan_logo.png"
          alt="泰坦科技"
        />
        <img
          class="ice-water-surface"
          src="../../assets/images/elements/kdan-water-surface.png"
          alt="水面"
        />
      </div>
      <div class="ice">
        <img
          id="titan"
          src="../../assets/images/elements/titan_logo.png"
          alt="kdan"
        />
        <img
          class="ice-water-surface"
          src="../../assets/images/elements/titan-water-surface.png"
          alt="水面"
        />
      </div>
    </div>
    <div class="penguins">
      <div class="penguin1">
        <img
          class="penguin"
          src="../../assets/images/elements/penguin1.png"
          alt="企鵝1"
        />
      </div>
      <div class="penguin2">
        <img
          class="penguin"
          src="../../assets/images/elements/penguin3.png"
          alt="企鵝2"
        />
      </div>
      <div class="penguin3">
        <img
          class="penguin"
          src="../../assets/images/elements/penguin2.png"
          alt="企鵝3"
        />
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
import TextPlugin from "gsap/TextPlugin";
export default {
  mounted() {
    gsap.registerPlugin(ScrollTrigger, TextPlugin);
    this.submarineUpAndDown();
    this.iceFloatUpAndDown();
    this.penguinFlap();
  },
  methods: {
    submarineUpAndDown() {
      gsap.to("#submarine", {
        y: 20,
        duration: 1.2,
        repeat: -1,
        yoyo: true,
      });
    },
    iceFloatUpAndDown() {
      gsap.to("#blockstudio", {
        y: 26,
        rotation: 15,
        yoyo: true,
        duration: 2,
        repeat: -1,
      });
      gsap.to("#kdan", {
        y: 22,
        rotation: -10,
        yoyo: true,
        duration: 2,
        repeat: -1,
        delay: 1,
      });
      gsap.to("#titan", {
        y: 20,
        rotation: 18,
        yoyo: true,
        duration: 2,
        repeat: -1,
        delay: 2,
      });
    },
    penguinFlap() {},
  },
};
</script>

<style lang="scss">
@mixin pad {
  @media (max-width: 768px) {
    @content;
  }
}

.home3 {
  height: 100vh;
  width: 100vw;
  background-color: #fff;
  background-image: url("../../assets/images/background/background3.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 80% center;
  position: relative;

  h1 {
    font-family: "Noto Sans TC", sans-serif;
    color: #2a99d9;
    font-size: 32px;
    font-weight: 400;
    line-height: 47px;
    position: absolute;
    top: 254px;
    left: 46vw;
  }

  .submarine-float {
    .submarine {
      position: absolute;
      bottom: 13vh;
      left: 20vw;
      height: 218px;
      width: 264px;
      z-index: 1;
    }

    .water-surface {
      position: absolute;
      bottom: 9.5vh;
      left: 20.5vw;
    }
  }

  .sponsors {
    position: absolute;
    width: 540px;
    display: flex;
    justify-content: space-between;
    top: 39vh;
    right: 37vw;

    .ice:nth-child(1) {
      position: relative;
    }

    .ice:nth-child(2) {
      position: relative;
    }

    .ice:nth-child(3) {
      position: relative;
    }

    .ice-water-surface {
      position: absolute;
      top: 100px;
      right: -20px;
    }
  }

  .penguins {
    position: absolute;
    top: 500px;
    right: 260px;
    display: flex;
    justify-content: space-between;
    width: 200px;

    .penguin1 {
      position: absolute;
      right: 4rem;
      bottom: 2rem;
    }

    .penguin2 {
      transform: scale(0.6, 0.6);
      transform: scaleX(-1);
      position: absolute;
      right: -1rem;
      bottom: 3.3rem;
    }

    .penguin3 {
      position: relative;
      position: absolute;
      right: -6rem;
      bottom: 6rem;
    }
  }
}
</style>
