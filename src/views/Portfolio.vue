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
      timer: 0,
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
          title: "父亲",
          body: "原本的我。矮矮小小 胆胆怯怯。不够坚强 不够自信。随着时间流逝。身子骨结实了。思维更加稳重了。现在活蹦乱跳的你。给了我莫大的。自信与勇气。面对多彩的生活。孩子的我。也走过一回孩子。现在由你。给我自信。陪伴年轻的你",
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
          title: "归年夜色sdfsdfds",
          body: "月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途。月色落圆花烟处。误入荷塘煤屑路。细语流年。惊觉烟火绽燃天渡。半生余途",
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
      this.isTitle = true;
      this.timer = setTimeout(() => {
        this.isProdu = true;
      }, 150);
    },
  },
  mounted() {
    this.isShow();
  },
  beforeDestroy() {
    clearTimeout(this.timer);
    this.isTitle = false;
    this.isProdu = false;
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