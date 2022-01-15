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
  img {
    width: 360px;
    height: 190px;
    border-radius: 7px;
    margin: 15px 0px;
  }

  .design {
    margin: 15px 0px;
    position: absolute;
    top: 0px;
    left: 0px;
    width: 360px;
    height: 190px;
    border-radius: 7px;
    background-color: #dba621;
    display: flex;
    justify-content: center;
    align-items: center;
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