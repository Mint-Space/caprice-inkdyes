<template>
  <div class="home">
    <div class="container">
      <div class="container-img">
        <transition name="home-into">
          <home-info v-show="isHome" />
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
import "animate.css";
import HomeInfo from "@/components/HomeInfo";
export default {
  name: "Home",
  components: {
    HomeInfo,
  },
  data() {
    return {
      isHome: false,
    };
  },
  methods: {
    isShow() {
      this.isHome = true;
    },
  },
  mounted() {
    this.isShow();
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
    }
  }
}
.home-into-enter-active {
  animation: fadeInRightBig 1s;
}
</style>