<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" :titles="titles" v-show="isTitle" />
    </transition>
    <div class="container-body">
      <transition name="lamp-into">
        <blog-lamp v-show="isLamp" />
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