<template>
  <div class="card" @mouseenter="moveIn" @mouseleave="moveOut">
    <div class="img">
      <img :src="poem.imgSrc" alt="" srcset="" align="middle" />
      <transition name="move">
        <div v-show="isShow" class="design">{{ poem.title }}</div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductionCard",
  props: {
    poemObj: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      isShow: false,
      poem: this.poemObj,
    };
  },
  methods: {
    moveIn() {
      this.isShow = true;
    },
    moveOut() {
      this.isShow = false;
    },
  },
};
</script>

<style lang="less" scoped>
.card {
  position: relative;
  width: 30%;
  height: 30%;
  // margin: 10px;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  .img {
    border-radius: 7px;
    width: 75%;
    height: 75%;
    overflow: hidden;
    margin-bottom: 20px;
    position: relative;
    background-position: center;
    background-size: cover;
    img {
      width: 100%;
      height: 100%;
      background-position: center;
      background-size: cover;
      object-fit: fill;
      // border-radius: 7px;
    }
    .design {
      position: absolute;
      margin: auto;
      top: 0px;
      width: 100%;
      height: 100%;
      border-radius: 7px;
      background-color: #dba621;
      color: #fff;
      font-size: 25px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  .move-enter-active {
    animation: move 1s ease;
  }
  .move-leave-active {
    animation: move 1s ease reverse;
  }
}

@keyframes move {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>