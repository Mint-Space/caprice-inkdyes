<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" v-show="isTitle" :titles="titles" />
    </transition>
    <div class="container-body">
      <transition name="produ-into">
        <production v-show="isProdu" />
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