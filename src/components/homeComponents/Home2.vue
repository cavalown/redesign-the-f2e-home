<template>
  <div class="home2">
    <div id="sections">
      <div id="panels-container">
        <!-- 互動式網頁設計:每週活動:1&2 -->
        <div class="panel" id="section1">
          <h2>互動式網頁設計</h2>
          <div class="dialog">
            <div class="mission" id="week1">
              <h3>Week1 <br />The F2E 活動網站設計<br />視差滾動</h3>
              <p>#版塊設計</p>
              <button>查看關卡細節</button>
            </div>
            <div class="mission" id="week2">
              <h3>Week2 <br />晚，我想來點點簽 <br />Canvas</h3>
              <p>#凱鈿行動科技</p>
              <button>查看關卡細節</button>
            </div>
          </div>
        </div>
        <!-- 每週活動:3 -->
        <div class="panel" id="section2">
          <div class="dialog">
            <div class="mission" id="week3">
              <h3>
                Week3 <br />
                Scrum 新手村 <br />JS draggable
              </h3>
              <p>#新加坡商鈦坦科技</p>
              <button>查看關卡細節</button>
            </div>
          </div>
        </div>
        <!-- 流程時間 -->
        <div class="panel" id="section3">
          <div class="time-section">
            <div class="title">
              <h4>開放報名</h4>
              <h4>各組別開賽</h4>
              <h4>登陸作品</h4>
              <h4>線上直播</h4>
            </div>
            <div class="time-line"></div>
            <div class="dots">
              <div class="dot"></div>
              <div class="dot"></div>
              <div class="dot"></div>
              <div class="dot"></div>
            </div>
            <div class="content">
              <p>
                10/13(四) 早上 11:00 - <br />
                11/6(日) 晚上 23:59
              </p>
              <p>
                UI組、團體組開賽10/31、 <br />
                前端組開賽 11/7
              </p>
              <p>
                10/31(一) 中午 12:00- <br />
                11/28(一) 中午 12:00
              </p>
              <p>11/3 - 11/24（每週四）</p>
            </div>
          </div>
        </div>
        <!-- 區區修煉已經無法滿足了嗎？還有比賽等著你！ -->
        <div class="panel" id="section4">
          <div class="rock">
            <p>區區修煉已經無法滿足了嗎？還有比賽等著你！</p>
          </div>
          <img src="../../assets/images/elements/Star.png" alt="海星" />
        </div>
        <!-- 評審機制 -->
        <div class="panel" id="section5">
        </div>
        <!-- 獎項 -->
        <div class="panel" id="section6">
          <div class="dialog">
            <div class="content">
              <h3>獎項</h3>
              <ul>
                <li>初選佳作 共六十位 <span>數位獎狀</span></li>
                <li>個人企業獎 共六位 <span>NTD 3,000/位</span></li>
                <li>團體企業獎 共三組 <span>NTD 10,000/組</span></li>
                <li>以上皆提供完賽數位獎狀</li>
              </ul>
            </div>
          </div>
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
      // const upPanels = gsap.utils.toArray("#panels-container .panel-up");
      gsap
        .to(panels, {
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
        })
        .to(".panel-up", {});
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
      }

      #section1 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -50px bottom;

        h2 {
          width: 50px;
          height: 400px;
          font-size: 36px;
          font-weight: 400;
          color: #ffffff;
          writing-mode: vertical-rl;
          letter-spacing: 20px;
          position: absolute;
          left: 2vw;
          bottom: 50vh;
        }

        .dialog {
          font-family: Zen Maru Gothic;
          line-height: 40px;
          text-align: left;
          letter-spacing: 0.3em;

          .mission {
            background-image: url("../../assets/images/elements/dialog-big.png");
            width: 434px;
            height: 313px;

            h3 {
              font-size: 24px;
              font-weight: 700;
              color: #245c80;
              padding-top: 30px;
              padding-left: 30px;
              letter-spacing: 0.3em;
            }

            p {
              font-size: 20px;
              font-weight: 400;
              color: #245c80;
              text-align: left;
              padding-top: 30px;
              padding-left: 30px;
              letter-spacing: 0.5em;
            }

            button {
              font-size: 16px;
              font-weight: 700;
              background-color: none;
              color: #245c80;
              border: #245c80 2px solid;
              border-radius: 6px;
              height: 45px;
              text-align: right;
              position: absolute;
              right: 30px;
              bottom: 70px;
            }
          }

          #week1 {
            position: absolute;
            right: 20vw;
            top: calc(250vh - 670px);
          }

          #week2 {
            position: absolute;
            right: 6vw;
            top: calc(250vh - 870px);
          }
        }
      }

      #section2 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: calc(-50px - 100vw) bottom;

        .dialog {
          font-family: Zen Maru Gothic;
          line-height: 40px;
          text-align: left;
          letter-spacing: 0.3em;

          .mission {
            background-image: url("../../assets/images/elements/dialog-big.png");
            width: 434px;
            height: 313px;

            h3 {
              font-size: 24px;
              font-weight: 700;
              color: #245c80;
              padding-top: 30px;
              padding-left: 30px;
              letter-spacing: 0.3em;
            }

            p {
              font-size: 20px;
              font-weight: 400;
              color: #245c80;
              text-align: left;
              padding-top: 30px;
              padding-left: 30px;
              letter-spacing: 0.5em;
            }

            button {
              font-size: 16px;
              font-weight: 700;
              color: #245c80;
              border: #245c80 2px solid;
              border-radius: 6px;
              height: 45px;
              text-align: right;
              position: absolute;
              right: 30px;
              bottom: 70px;
            }
          }

          #week3 {
            position: absolute;
            left: 440px;
            top: calc(250vh - 720px);
          }
        }
      }

      #section3 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -202vw bottom;

        .time-section {
          position: relative;
          width: 90vw;
          margin: 0 auto;
          bottom: 500px;

          .title {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;

            h4 {
              font-size: 32px;
              font-weight: 700;
              color: #ffffff;
            }
          }

          .time-line {
            height: 8px;
            border-bottom: 5px rgba(135, 212, 250, 0.29) solid;
            width: 80vw;
            margin: 0 auto;
          }

          .dots {
            width: 80vw;
            height: 15px;
            display: flex;
            justify-content: space-between;
            margin: 0 auto;
            position: absolute;
            left: 5vw;
            top: 4em;

            .dot {
              width: 15px;
              height: 15px;
              border: 1px solid rgb(93, 182, 227);
              border-radius: 50%;
              background-color: rgb(93, 182, 227);
              margin-bottom: 20px;
            }
          }

          .content {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;

            p {
              font-size: 20px;
              font-weight: 700;
              color: #ffffff;
              text-align: left;
              line-height: 32px;
            }
          }
        }
      }

      #section4 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 800vw;
        background-position: -404vw bottom;

        .rock {
          background: url("../../assets/images/background/rock.png") no-repeat;
          background-size: cover;
          height: 100vh;
          width: 70vw;
          position: absolute;
          bottom: 0;
          left: 30vw;

          p {
            font-size: 32px;
            font-weight: 700;
            letter-spacing: 10px;
            color: #ffffff;
            margin-top: 50vh;
          }
        }

        img {
          height: 117px;
          position: absolute;
          bottom: 40px;
          left: 50vw;
        }
      }

      #section5 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -365vw bottom;
      }

      #section6 {
        background-image: url("../../assets/images/background/background2.png");
        background-size: 600vw;
        background-position: -470vw 0px;

        .dialog {
          font-family: Zen Maru Gothic;
          line-height: 40px;
          text-align: left;
          letter-spacing: 0.3em;
          background-image: url("../../assets/images/elements/dialog-big.png");
          width: 434px;
          height: 313px;
          transform: rotate(180deg);
          position: absolute;
          bottom: 20vh;
          left: 20vw;

          .content {
            transform: rotate(180deg);
            padding-bottom: 30px;

            h3 {
              font-size: 32px;
              font-weight: 700;
              color: #245c80;
              padding-left: 30px;
              letter-spacing: 0.3em;
              margin-bottom: 20px;
            }

            ul>li {
              margin-left: 60px;
              list-style: disc;
              font-size: 20px;
              font-weight: 700;
              color: #245c80;
              text-align: left;
              letter-spacing: 0.1rem;

              span {
                color: #e3b40c;
              }
            }
          }
        }
      }
    }
  }
}
</style>
