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
        <img src="../../assets/images/elements/arrow-down.png" alt="請向下滾動" />
      </div>
    </div>
    <div class="submarine-float">
      <img class="submarine" src="../../assets/images/elements/submarine1.png" alt="潛水艇" />
      <img class="water-surface" src="../../assets/images/elements/water.png" alt="潛水艇接處水面" />
    </div>
  </div>
</template>

<script>
import Navbar from "../Navbar.vue";
export default {
  components: {
    Navbar,
  },
};
</script>

<style lang="scss">
.home1 {
  height: 981px;
  background-image: url("../../assets/images/background/background1.png");

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
      top: 580px;
      left: 255px;
    }
  }
}
</style>
