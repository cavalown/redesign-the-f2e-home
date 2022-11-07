<template>
  <div class="home3">
    <div class="submarine-float">
      <img class="submarine" id="submarine" src="../../assets/images/elements/submarine1.png" alt="潛水艇" />
      <img class="water-surface" src="../../assets/images/elements/water-surface2.png" alt="潛水艇接處水面" />
    </div>
    <div class="sponsors">
      <div class="ice">
        <img id="blockstudio" src="../../assets/images/elements/blockstudio_logo.png" alt="板塊設計" />
        <img class="ice-water-surface" src="../../assets/images/elements/blockstudio-water-surface.png" alt="水面" />
      </div>
      <div class="ice">
        <img id="kdan" src="../../assets/images/elements/kdan_logo.png" alt="泰坦科技" />
        <img class="ice-water-surface" src="../../assets/images/elements/kdan-water-surface.png" alt="水面" />
      </div>
      <div class="ice">
        <img id="titan" src="../../assets/images/elements/titan_logo.png" alt="kdan" />
        <img class="ice-water-surface" src="../../assets/images/elements/titan-water-surface.png" alt="水面" />
      </div>
    </div>
    <div class="penguins">
      <div class="penguin1">
        <img class="penguin" src="../../assets/images/elements/penguin1.png" alt="企鵝1">
      </div>
      <div class="penguin2">
        <img class="penguin" src="../../assets/images/elements/penguin3.png" alt="企鵝2">
      </div>
      <div class="penguin3">
        <img class="penguin" src="../../assets/images/elements/penguin2.png" alt="企鵝3">
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
        rotate: 25,
        yoyo: true,
        duration: 2,
        repeat: -1,
      });
      gsap.to("#kdan", {
        y: 22,
        rotate: 22,
        yoyo: true,
        duration: 2,
        repeat: -1,
        delay: 1,
      });
      gsap.to("#titan", {
        y: 20,
        rotate: 18,
        yoyo: true,
        duration: 2,
        repeat: -1,
        delay: 2,
      });
    },
    penguinFlap() {
    }
  },
};
</script>

<style lang="scss">
.home3 {
  height: 981px;
  background-image: url("../../assets/images/background/background3.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: absolute;

  .submarine-float {
    .submarine {
      position: absolute;
      top: 580px;
      left: 255px;
      height: 218px;
      width: 264px;
    }

    .water-surface {
      position: absolute;
      top: 780px;
      left: 255px;
    }
  }

  .sponsors {
    width: 620px;
    display: flex;

    .ice:nth-child(1) {
      position: absolute;
      top: 530px;
      left: 580px;
    }

    .ice:nth-child(2) {
      position: absolute;
      top: 530px;
      left: 800px;
    }

    .ice:nth-child(3) {
      position: absolute;
      top: 530px;
      left: 1020px;
    }

    .ice-water-surface {
      position: absolute;
      top: 100px;
      right: -30px;
    }
  }

  .penguins {
    position: absolute;
    top: 500px;
    right: 260px;

    .penguin1 {
      position: absolute;
      top: 20px;
      right: 130px;
    }

    .penguin2 {
      position: absolute;
      top: -30px;
      right: 60px;
      transform: scale(0.6, 0.6);
      transform: scaleX(-1);
    }

    .penguin3 {
      position: absolute;
      top: -5px;
      right: 10px;
    }
  }
}
</style>
