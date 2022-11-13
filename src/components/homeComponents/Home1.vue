<template>
  <div class="home1">
    <div class="title">
      <h1>互動網頁設計</h1>
      <ul>
        <li>UI Design</li>
        <li>FrontEnd</li>
      </ul>
      <p class="hint-word">滾動開始</p>
      <div class="hint">
        <img id="hint-arrow" src="../../assets/images/elements/arrow-down.png" alt="請向下滾動" />
      </div>
    </div>
    <div class="submarine-float">
      <img class="submarine" id="submarine" src="../../assets/images/elements/submarine1.png" alt="潛水艇" />
      <img class="water-surface" src="../../assets/images/elements/water-surface1.png" alt="潛水艇接處水面" />
    </div>
    <div class="birds">
      <div class="bird1">
        <img class="bird-left" src="../../assets/images/elements/bird-left.svg" alt="鳥左翅" />
        <img class="bird-right" src="../../assets/images/elements/bird-right.svg" alt="鳥右翅" />
      </div>
      <div class="bird2">
        <img class="bird-left" src="../../assets/images/elements/bird-left.svg" alt="鳥左翅" />
        <img class="bird-right" src="../../assets/images/elements/bird-right.svg" alt="鳥右翅" />
      </div>
      <div class="bird3">
        <img class="bird-left" src="../../assets/images/elements/bird-left.svg" alt="鳥左翅" />
        <img class="bird-right" src="../../assets/images/elements/bird-right.svg" alt="鳥右翅" />
      </div>
      <div class="bird4">
        <img class="bird-left" src="../../assets/images/elements/bird-left.svg" alt="鳥左翅" />
        <img class="bird-right" src="../../assets/images/elements/bird-right.svg" alt="鳥右翅" />
      </div>
      <div class="bird5">
        <img class="bird-left" src="../../assets/images/elements/bird-left.svg" alt="鳥左翅" />
        <img class="bird-right" src="../../assets/images/elements/bird-right.svg" alt="鳥右翅" />
      </div>
      <div class="bird6">
        <img class="bird-left" src="../../assets/images/elements/bird-left.svg" alt="鳥左翅" />
        <img class="bird-right" src="../../assets/images/elements/bird-right.svg" alt="鳥右翅" />
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
    this.arrowRun();
    this.submarineUpAndDown();
    this.birdsFly();
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
    birdsFly() {
      gsap.to(".bird-left", {
        rotation: -50,
        yoyo: true,
        duration: 0.3,
        repeat: -1,
      });
      gsap.to(".bird-right", {
        rotation: 50,
        yoyo: true,
        duration: 0.3,
        repeat: -1,
      });
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

.home1 {
  width: 100vw;
  height: 100vh;
  overflow-x: hidden;
  background-color: #fff;
  background: url("../../assets/images/background/background1.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;

  @include phone {
    // url(img_flwr.gif) right bottom no-repeat,url(paper.gif) left top repeat;
    // background-color: #3eb1ee;
    background-image: url("../../assets/images/background/bg-mobile1.svg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }

  .title {
    padding-top: 206px;

    @include pad {
      padding-top: 140px;
    }

    @include phone {
      padding-top: 100px;
    }

    h1 {
      margin-bottom: 35px;
      color: #2a99d9;
      font-size: 36px;
      font-weight: 400;
      line-height: 18px;
      font-family: "Noto Sans TC", sans-serif;

      @include phone {
        margin-bottom: 0;
        text-align: justify;
        padding-left: 30px;
        padding-right: 30px;
        padding-top: 0;

        &::after {
          display: inline-block;
          width: 100%;
          content: "";
        }
      }
    }

    ul {
      width: 327px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      color: #2a99d9;
      font-size: 24px;
      font-weight: 400;

      @include phone {
        margin-top: 15px;
        width: calc(100% - 60px);
        letter-spacing: 5px;
      }
    }

    .hint-word {
      margin-top: 29px;
      color: #2a99d9;
      font-size: 14px;
      font-weight: 700;

      @include phone {
        display: none;
      }
    }

    .hint {
      margin: 0 auto;
      margin-top: 15px;
      width: 34px;
      height: 50px;
      border-radius: 80px;
      background-color: #fff;

      @include phone {
        display: none;
      }
    }
  }

  .submarine-float {
    .submarine {
      position: absolute;
      bottom: 21vh;
      left: 20vw;
      height: 218px;
      width: 264px;

      @include phone {
        width: calc(264px * 0.8);
        height: calc(218px * 0.8);
        left: 28vw;
        bottom: 30vh;
      }
    }

    .water-surface {
      position: absolute;
      bottom: 17.5vh;
      left: 20.5vw;

      @include phone {
        width: calc(264px * 0.8);
        left: 29vw;
        bottom: 26.7vh;
      }
    }
  }

  .birds {
    width: 700px;
    height: 50vh;
    position: relative;
    margin: 0 auto;
    bottom: 17rem;

    .bird1 {
      width: 30px;
      position: relative;
      top: 130px;
      rotate: 20deg;

      img:nth-child(1) {
        width: 0.9em;
        left: 1px;
      }

      img:nth-child(2) {
        width: 0.9em;
      }
    }

    .bird2 {
      width: 30px;
      position: relative;
      left: 80px;
      top: 160px;
      rotate: 10deg;

      img:nth-child(1) {
        width: 0.9em;
        left: 1px;
      }

      img:nth-child(2) {
        width: 0.9em;
      }
    }

    .bird3 {
      width: 50px;
      position: relative;
      left: 120px;
      top: 10px;
      rotate: 10deg;

      img:nth-child(1) {
        width: 1.3em;
        left: 1px;
      }

      img:nth-child(2) {
        width: 1.3em;
      }
    }

    .bird4 {
      width: 50px;
      position: relative;
      left: 410px;
      top: -100px;
      rotate: 40deg;

      img:nth-child(1) {
        width: 1.3em;
        left: 1px;
      }

      img:nth-child(2) {
        width: 1.3em;
      }
    }

    .bird5 {
      width: 50px;
      position: relative;
      left: 460px;
      top: -20px;
      rotate: 30deg;

      img:nth-child(1) {
        width: 1.3em;
        left: 1px;
      }

      img:nth-child(2) {
        width: 1.3em;
      }
    }

    .bird6 {
      width: 50px;
      position: relative;
      left: 560px;
      top: -50px;
      rotate: 30deg;

      img:nth-child(1) {
        width: 1.4em;
      }

      img:nth-child(2) {
        width: 1.4em;
      }
    }
  }
}
</style>
