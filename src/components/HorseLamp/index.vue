<template>
  <div class="horse-lamp">
    <div class="lamp-list">
      <transition-group tag="div" name="banner">
        <div
          class="lamp-items"
          v-for="(item, index) in 3"
          v-show="num == index"
          :key="index"
        >
          <img class="lamp-img" src="../../assets/sky.jpeg" alt="" />
          <div class="poem">
            <div class="poem-title">归年夜色</div>
            <div class="poem-bady">
              <p>月色落圆花烟处</p>
              <p>误入荷塘煤屑路</p>
              <p>细语流年</p>
              <p>细语流年</p>
              <p>惊觉烟火绽燃天渡</p>
              <p>半生余途</p>
            </div>
            <div class="poem-author">墨染</div>
          </div>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<script>
export default {
  name: "HorseLamp",
  data() {
    return {
      num: 0, // 默认显示第几个
      animateTime: 5000, // 要和 css 的过渡一致
      self,
    };
  },
  mounted() {
    this.play(); // 初始的时候加载
  },
  methods: {
    autoPlay() {
      // num自增，通过判断 num 和 index 相不相等，来显示对应 index 的banner
      this.num++;
      if (this.num == 3) {
        this.num = 0;
      }
    },
    play() {
      // 设置定时器，让banner显示隐藏
      this.self = setInterval(this.autoPlay, this.animateTime);
    },
  },
  destroyed() {
    clearInterval(this.self);
  },
};
</script>

<style lang="less" scoped>
.horse-lamp {
  box-shadow: 3px 3px 6px 3px rgba(126, 126, 126, 0.3);
  overflow: hidden;
  .lamp-list {
    display: flex;
    flex-flow: row;
    position: relative;
    .lamp-items {
      width: 700px;
      height: 400px;
      position: absolute;
      top: 0;
      .lamp-img {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0px;
        left: 0px;
      }
      .poem {
        position: absolute;
        bottom: 0px;
        right: 0px;
        text-align: left;
        padding: 15px 55px;
        .poem-title {
          font-size: 22px;
          font-weight: bold;
          color: rgb(59, 59, 59);
          padding: 6px 0px;
        }
        .poem-body {
          font-size: 18px;
          font-weight: bolder;
          color: rgb(83, 83, 83);
        }
        .poem-author {
          font-size: 16px;
          text-align: right;
          font-weight: lighter;
          color: rgb(136, 136, 136);
        }
      }
    }
  }
}

.banner-enter-active,
.banner-leave-active {
  transition: all 5s ease-in-out;
}

.banner-enter {
  opacity: 0;
  left: 700px;
}
.banner-enter-to {
  opacity: 1;
  left: 0px;
}

.banner-leave {
  opacity: 1;
  left: 0px;
}
.banner-leave-to {
  opacity: 0;
  left: -700px;
}
</style>