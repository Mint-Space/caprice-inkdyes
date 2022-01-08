<template>
  <div class="home">
    <div class="container">
      <div class="container-img">
        <div class="container-info">
          <div class="hello">HELLO!</div>
          <div class="info-iam">
            <h2>我是</h2>
            <span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>
            <h2>一名设计师</h2>
          </div>
          <div class="info-desic">
            这里是文字区块，您可以点击文字上的编辑按钮更改这里的文字。广告集,搜集全球经典广告,有创意、爱公益、会搞笑,一个视频,几张图片,展现每一个精彩瞬
            间,与你分享每一分的快乐和感动！
          </div>
          <div class="info-button">
            <div class="info-button-learn">了解更多</div>
            <transition name="move">
              <div
                ref="production"
                @mouseover="mouseIn"
                @mouseleave="mouseOut"
                class="info-button-production"
              >
                作品集
              </div>
            </transition>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {};
  },
  methods: {
    mouseIn(e) {
      // this.show = !this.show;
      // this.$refs.production.className =
      //   "move-enter-active info-button-production:after";
      this.$refs.production.className = "info-button-production-move-in:after";
    },
    mouseOut(e) {
      this.$refs.production.className = "info-button-production-move-out:after";
      // this.show = !this.show;
      // this.$refs.production.className =
      //   "move-leave-active info-button-production:after";
    },
  },
};
</script>
<style lang="less" scoped>
.home {
  width: 100%;
  height: 100%;
  .container {
    width: 100%;
    height: 100%;
    .container-img {
      width: 100%;
      height: 100%;
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
      background-image: url("../assets/sky.jpeg");
      display: flex;
      flex-flow: row;
      justify-content: center;
      align-items: center;
      .container-info {
        width: 50%;
        height: 40%;
        display: flex;
        flex-flow: column;
        justify-content: flex-start;
        align-items: flex-start;
        .hello {
          font-size: 24px;
          color: #fff;
        }
        div {
          padding: 8px;
        }
        .info-iam {
          display: flex;
          justify-content: center;
          align-items: center;
          font-size: 36px;
          color: #fff;
        }
        .info-desic {
          color: #fff;
          text-align: left;
        }

        .info-button {
          width: 100%;
          height: 25%;
          display: flex;
          flex-flow: row;
          justify-content: space-between;
          align-items: center;
          div {
            border-radius: 35px;
            padding: 20px 90px;
            background-color: orange;
            color: #fff;
            border: orange 2px solid;
          }
          .info-button-production {
            background-color: rgba(255, 166, 0, 0);
            border: orange 2px solid;
            position: relative;
          }
          
          @keyframes move {
            0% {
              transform: translateX(0%);
            }
            100% {
              transform: translateX(100%);
            }
          }
        }
      }
    }
  }
}
</style>