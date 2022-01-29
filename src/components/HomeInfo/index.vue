<template>
  <div class="container-info">
    <div class="hello">HELLO!</div>
    <div class="info-iam">
      <div class="info-iam-is">我是</div>
      <div class="load-text">
        <vue-typed-js
          :strings="['一名设计师', '您身边的交互设计师']"
          :loop="true"
        >
          <span class="typing"></span>
        </vue-typed-js>
      </div>
    </div>
    <div class="info-desic">
      这里是文字区块，您可以点击文字上的编辑按钮更改这里的文字。广告集,搜集全球经典广告,有创意、爱公益、会搞笑,一个视频,几张图片,展现每一个精彩瞬
      间,与你分享每一分的快乐和感动！
    </div>
    <div class="info-button">
      <div class="info-button-learn" @click="toAbout()">了解更多</div>
      <div
        @mouseover="mouseIn"
        @mouseleave="mouseOut"
        class="info-button-production"
        @click="toProduction()"
      >
        作品集
        <transition name="move-into">
          <span class="info-button-production-span" v-show="isShowSpan"></span>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
import { VueTypedJs } from "vue-typed-js";
export default {
  name: "HomeInfo",
  components: {
    VueTypedJs,
  },
  data() {
    return {
      isShowSpan: false,
    };
  },
  methods: {
    toProduction() {
      this.$router.push({
        name: "Portfolio",
      });
    },
    toAbout() {
      this.$router.push({
        name: "About",
      });
    },
    mouseIn() {
      this.isShowSpan = true;
    },
    mouseOut() {
      this.isShowSpan = false;
    },
  },
  mounted() {},
  destroyed() {},
};
</script>
<style lang="less" scoped>
.container-info {
  width: 35%;
  height: 40%;
  display: flex;
  flex-flow: column;
  justify-content: space-between;
  align-items: flex-start;
  box-sizing: border-box;
  .hello {
    font-size: 24px;
    color: #fff;
    padding: 0px;
    display: flex;
    justify-content: flex-start;
  }
  .info-iam {
    display: flex;
    justify-content: space-between;
    width: 100%;
    font-size: 40px;
    color: #fff;
    .info-iam-is {
      width: 25%;
      display: flex;
      justify-content: flex-start;
    }
    .load-text {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      width: 75%;
      color: #dba621;
      .typing {
        font-size: 40px;
        display: flex;
        justify-content: flex-start;
        align-items: center;
      }
    }
  }
  .info-desic {
    color: #fff;
    text-align: left;
    display: flex;
    justify-content: flex-start;
  }

  .info-button {
    width: 100%;
    height: 25%;
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: center;
    padding: 0px;
    .info-button-learn {
      border-radius: 35px;
      padding: 20px 90px;
      background-color: #dba621;
      color: #fff;
      border: #dba621 2px solid;
    }
    .info-button-production {
      background-color: #dba62100;
      color: #fff;
      border-radius: 35px;
      padding: 20px 90px;
      border: #dba621 2px solid;
      position: relative;
      overflow: hidden;
      z-index: 1;
      .info-button-production-span {
        position: absolute;
        top: 0px;
        left: 0px;
        width: 100%;
        height: 100%;
        background-color: #dba621;
        z-index: -1;
      }
    }

    .move-into-enter-active {
      animation: moveInLeft 0.5s;
    }
    .move-into-leave-active {
      animation: moveOutRight 0.5s;
    }
    @keyframes moveInLeft {
      from {
        transform: translate3d(-100%, 0, 0);
      }

      to {
        transform: translate3d(0, 0, 0);
      }
    }
    @keyframes moveOutRight {
      from {
        transform: translate3d(0, 0, 0);
      }

      to {
        transform: translate3d(100%, 0, 0);
      }
    }
  }
}
</style>