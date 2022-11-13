<template>
  <div class="home2">
    <!-- <div id="section0">
      <h2>section0</h2>
    </div> -->
    <div id="sections">
      <div id="panels-container">
        <div class="panel" id="section1">
          <h2>section1</h2>
        </div>
        <div class="panel" id="section2">
          <h2>section2</h2>
        </div>
        <div class="panel" id="section3">
          <h2>section3</h2>
        </div>
        <div class="panel" id="section4">
          <h2>section4</h2>
        </div>
        <div class="panel" id="section5">
          <h2>section5</h2>
        </div>
        <div class="panel" id="section6">
          <h2>section6</h2>
        </div>
      </div>
    </div>
    <div class="submarine-container">
      <img class="submarine" id="submarine-in-water" src="../../assets/images/elements/submarine2.png" alt="潛水艇" />
      <img class="propeller" id="propeller" src="../../assets/images/elements/propeller.png" alt="" />
    </div>
  </div>
</template>

<script>
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
export default {
  mounted() {
    gsap.registerPlugin(ScrollTrigger);
    this.propellerSpin();
    this.scrollBackground();
  },
  methods: {
    scrollBackground() {
      const panelsContainer = document.querySelector("#panels-container");
      const panels = gsap.utils.toArray("#panels-container .panel");
      gsap.to(panels, {
        xPercent: -100 * (panels.length - 1),
        ease: "none",
        scrollTrigger: {
          trigger: "#panels-container",
          pin: true,
          start: "bottom bottom",
          scrub: 1,
          snap: {
            snapTo: 1 / (panels.length - 1),
            inertia: false,
            duration: { min: 0.1, max: 1 },
          },
          end: () => "+=" + (panelsContainer.offsetWidth - window.innerWidth),
        },
      });
    },
    propellerSpin() {
      gsap.to("#propeller", {
        rotationX: 360,
        duration: 0.1,
        yoyo: true,
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

.home2 {
  width: 100vw;
  height: 200vh;
  background-color: #ffffff;

  @include pad {
    height: 2541px;
    overflow-y: hidden;
    position: bottom;
  }

  @include phone {
    height: 2541px;
  }

  h2 {
    font-size: 56px;
    font-weight: 600;
    margin: 0 auto;
    margin-top: 2000px;
    margin-left: 500px;
  }

  .submarine-container {
    position: absolute;
    bottom: 21vh;
    left: 20vw;
    bottom: 800px;

    .submarine {
      height: 132px;
      width: 264px;

      @include phone {
        width: calc(264px * 0.8);
        height: calc(218px * 0.8);
        left: 28vw;
        bottom: 30vh;
      }
    }

    .propeller {
      width: 9px;
      position: absolute;
      bottom: 36px;
      left: 0;
    }
  }

  #section0 {
    width: 100vw;
    height: 100vh;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    background-image: url("../../assets/images/background/background2.png");
    background-position: left left;
  }

  #sections {
    z-index: 0;
    position: absolute;
    border: none;
    height: 250vh;

    #panels-container {
      width: 600vw;
      height: 250vh;
      display: flex;
      flex-wrap: nowrap;

      .panel {
        width: 100vw;
        height: 250vh;
        background-color: #3eb1ee;
      }

      #section1 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -50px bottom;
      }

      #section2 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: calc(-50px - 100vw) bottom;
      }

      #section3 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -200vw bottom;
      }

      #section4 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -300vw bottom;
      }

      #section5 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -400vw bottom;
      }

      #section6 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -500vw bottom;
      }
    }
  }
}
</style>
