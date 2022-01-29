<template>
  <div class="horse-lamp">
    <div class="lamp-list">
      <transition-group tag="div" name="banner">
        <div
          class="lamp-items"
          v-for="poem in poemList"
          v-show="num == poem.id"
          :key="poem.id"
        >
          <img class="lamp-img" :src="poem.imgSrc" alt="" />
          <div class="poem">
            <div class="poem-level" v-if="!isChangeLayout(poem.id)">
              <div class="poem-title-level">{{ poem.title }}</div>
              <div class="poem-bady-level">
                <div
                  class="poem-bady-level-div"
                  v-for="(poemSentence, index) in poemSentenceList(poem.id)"
                  :key="index"
                >
                  {{ poemSentence }}
                </div>
              </div>
              <div class="poem-author-level">{{ poem.author }}</div>
            </div>
            <div class="poem-vertical" v-if="isChangeLayout(poem.id)">
              <div class="poem-title-vertical">{{ poem.title }}</div>
              <div
                class="poem-body-vertical"
                v-for="(poemSentence, index) in poemSentenceList(poem.id)"
                :key="index"
              >
                {{ poemSentence }}
              </div>
              <div class="poem-author-vertical">{{ poem.author }}</div>
            </div>
          </div>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<script>
export default {
  name: "HorseLamp",
  props: {
    poemListArr: {
      type: Array,
      required: true,
    },
    poemId: {
      type: Number,
      require: true,
    },
  },
  data() {
    return {
      timer: 0,
      poemSentenceListLength: 0,
      poemSentenceArray: [],
      num: 0, // 默认显示第几个
      animateTime: 6000, // 要和 css 的过渡一致
      self,
      poemList: this.poemListArr,
    };
  },
  mounted() {
    this.run();
  },
  computed: {
    isChangeLayout() {
      return (id) => {
        if (this.poemSentenceList(id).length >= 12) {
          return true;
        } else if (this.poemSentenceList(id).length <= 12) {
          return false;
        }
      };
    },
    poemSentenceList() {
      var array = [];
      return (index) => {
        array = this.poemList[index].body.split("。");
        this.poemSentenceArray = array;
        return array;
      };
    },
  },
  methods: {
    run() {
      if (this.poemId == 0) {
        this.num = 1;
        this.timer = setTimeout(this.play(), this.animateTime);
      } else {
        this.num = this.poemId;
        this.timer = setTimeout(this.play(), this.animateTime);
      }
    },
    autoPlay() {
      // num自增，通过判断 num 和 index 相不相等，来显示对应 index 的banner
      this.num++;
      if (this.num == this.poemList.length) {
        this.num = 0;
      }
    },
    play() {
      // 设置定时器，让banner显示隐藏
      this.self = setInterval(this.autoPlay, this.animateTime);
    },
  },
  destroyed() {
    clearTimeout(this.timer);
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
        z-index: -1;
      }
      .poem {
        display: flex;
        flex-flow: row-reverse;
        justify-content: flex-start;
        align-items: flex-start;
        z-index: 1;
        .poem-level {
          position: absolute;
          bottom: 0px;
          right: 0px;
          text-align: left;
          padding: 15px 55px;
          .poem-title-level {
            text-align: left;
            font-size: 20px;
            font-weight: bold;
            color: rgb(59, 59, 59);
            padding: 6px 0px;
          }
          .poem-body-level {
            font-size: 16px;
            font-weight: bolder;
            color: rgb(83, 83, 83);
          }
          .poem-author-level {
            font-size: 14px;
            text-align: right;
            font-weight: lighter;
            color: rgb(136, 136, 136);
          }
        }
        .poem-vertical {
          text-align: right;
          padding: 15px 55px;
          display: flex;
          flex-flow: row-reverse;
          justify-content: flex-start;
          .poem-title-vertical {
            writing-mode: vertical-lr;
            display: flex;
            flex-flow: column;
            justify-content: flex-start;
            align-items: flex-start;
            font-size: 20px;
            font-weight: bold;
            color: rgb(59, 59, 59);
            // padding: 6px 0px;
          }
          .poem-body-vertical {
            font-size: 16px;
            font-weight: lighter;
            color: rgb(83, 83, 83);
            display: flex;
            flex-flow: row-reverse;
            justify-content: flex-end;
            writing-mode: vertical-lr;
            align-items: flex-start;
          }
          .poem-author-vertical {
            writing-mode: vertical-rl;
            font-size: 14px;
            font-weight: lighter;
            color: rgb(136, 136, 136);
          }
        }
      }
    }
  }
}

.banner-enter-active,
.banner-leave-active {
  transition: all 3s ease-in-out;
  transition-delay: 3s;
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