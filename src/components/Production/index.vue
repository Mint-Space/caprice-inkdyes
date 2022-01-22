<template>
  <div class="production">
    <div class="box">
      <production-card
        class="items"
        @click.native="handleClick"
        v-for="poem in poemList"
        :key="poem.id"
        :poemObj="poem"
      />
    </div>
    <transition name="jump">
      <div v-show="isShowCard" class="hidden-card" @click.self="hiddenCard">
        <horse-lamp class="horse-lamp" :poemListArr="poemList" />
      </div>
    </transition>
  </div>
</template>

<script>
import ProductionCard from "@/components/ProductionCard";
import HorseLamp from "@/components/HorseLamp";
export default {
  name: "Production",
  components: {
    ProductionCard,
    HorseLamp,
  },
  data() {
    return {
      isShowCard: false,
      poemList: [
        {
          id: "0",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: "1",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/image/20200411/20200411153721_42156.jpg",
        },
        {
          id: "2",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: "3",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: "4",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/image/20200411/20200411153721_42156.jpg",
        },
        {
          id: "5",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: "6",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: "7",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/image/20200411/20200411153721_42156.jpg",
        },
        {
          id: "8",
          title: "归年夜色",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。",
          author: "墨染",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
      ],
    };
  },
  methods: {
    handleClick() {
      this.isShowCard = true;
    },
    hiddenCard() {
      this.isShowCard = false;
    },
  },
  mounted() {},
  destroyed() {},
};
</script>

<style lang="less" scoped>
.production {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  // padding: 40px 0px;
  box-sizing: border-box;
  .box {
    width: 70%;
    height: 50%;
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
  }
  .hidden-card {
    position: absolute;
    width: 100vw;
    height: 100vh;
    top: 0px;
    left: 0px;
    // border-radius: 7px;
    background: #f0f0f0f5;
    display: flex;
    justify-content: center;
    align-items: center;
    .horse-lamp {
      width: 700px;
      height: 400px;
      //   filter: blur(2px);
    }
  }
}

.jump-enter-active {
  animation: jump 1s ease;
}
.jump-leave-active {
  animation: jump 1s ease reverse;
}
@keyframes jump {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>