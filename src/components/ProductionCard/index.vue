<template>
  <div class="card" @mouseenter="moveIn" @mouseleave="moveOut">
    <img src="../../assets/sky.jpeg" alt="" srcset="" />
    <transition name="move">
      <div v-show="isShow" class="design">设计作品</div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "ProductionCard",
  data() {
    return {
      isShow: false,
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
  width: 26%;
  height: 15%;
  margin: 10px;
  box-sizing: border-box;

  img {
    width: 100%;
    height: auto;
    border-radius: 7px;
    background-size: cover;
    background-position: center;
  }

  .design {
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100%;
    height: 100%;
    border-radius: 7px;
    background-color: #dba621;
    color: #fff;
    font-size: 25px;
    display: flex;
    justify-content: center;
    align-items: center;
    box-sizing: border-box;
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