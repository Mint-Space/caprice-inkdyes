<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" v-show="isTitle" :titles="titles" />
    </transition>
    <div class="container-body">
      <transition name="produ-into">
        <production v-show="isProdu" :poemList="poemList" />
      </transition>
    </div>
  </div>
</template>

<script>
import Titles from "@/components/Title";
import Production from "@/components/Production";
export default {
  name: "Portfolio",
  components: {
    Titles,
    Production,
  },
  data() {
    return {
      isTitle: false,
      isProdu: false,
      titles: {
        title: ["MY", "PROTFOLIO"],
        describe: "我的往期作品展示",
      },
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
    isShow() {
      setTimeout(() => {
        this.isProdu = true;
      }, 150);
      this.isTitle = true;
    },
  },
  mounted() {
    this.isShow();
  },
};
</script>

<style lang="less" scoped>
.container {
  .container-title {
    height: 30vh;
  }
  .container-body {
    height: 70vh;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
}
.title-into-enter-active,
.produ-into-enter-active {
  animation: fadeInRightBig 1s;
}
</style>