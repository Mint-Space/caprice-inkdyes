<template>
  <div class="home">
    <div class="container">
      <transition name="img-into">
        <div class="container-img" v-show="isImg">
          <transition name="home-into">
            <home-info v-show="isHome" />
          </transition>
        </div>
      </transition>
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
      isImg: false,
      isHome: false,
    };
  },
  methods: {
    isShow() {
      this.isImg = true;
      setTimeout(() => {
        this.isHome = true;
      }, 150);
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
.img-into-enter-active {
  animation: fadeIn 1s;
}
</style>