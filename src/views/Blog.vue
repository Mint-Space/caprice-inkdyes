<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" :titles="titles" v-show="isTitle" />
    </transition>
    <div class="container-body">
      <transition name="lamp-into">
        <blog-lamp v-if="isLamp" :blogCardList="blogCardList" />
      </transition>
    </div>
  </div>
</template>

<script>
import Titles from "@/components/Title";
import BlogLamp from "@/components/BlogLamp";
export default {
  name: "Blog",
  components: {
    Titles,
    BlogLamp,
  },
  data() {
    return {
      isTitle: false,
      isLamp: false,
      titles: {
        title: ["BL", "OG"],
        describe: "有关网页设计和开发的技巧",
      },
      blogCardList: [
        {
          id: 1,
          title: "当年发生",
          date: "2020-12-14",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: 2,
          title: "发放",
          date: "2020-10-14",
          imgSrc:
            "https://www.toopic.cn/public/uploads/image/20200411/20200411153721_42156.jpg",
        },
        {
          id: 3,
          title: "来接你，康师傅",
          date: "2020-12-14",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: 4,
          title: "瓦尔访问",
          date: "2024-12-14",
          imgSrc:
            "https://www.toopic.cn/public/uploads/image/20200411/20200411153721_42156.jpg",
        },
        {
          id: 5,
          title: "阿双方尽快两年里",
          date: "2020-12-14",
          imgSrc:
            "https://www.toopic.cn/public/uploads/small/16388607525163886075231.jpg",
        },
        {
          id: 6,
          title: "东方女神",
          date: "2020-12-14",
          imgSrc:
            "https://www.toopic.cn/public/uploads/image/20200411/20200411153721_42156.jpg",
        },
      ],
    };
  },
  methods: {
    isShow() {
      this.isTitle = true;
      setTimeout(() => {
        this.isLamp = true;
      }, 150);
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
    height: 60vh;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
}
.title-into-enter-active,
.lamp-into-enter-active {
  animation: fadeInRightBig 1s;
}
</style>