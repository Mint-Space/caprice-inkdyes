<template>
  <div class="production">
    <div class="box">
      <production-card
        class="items"
        @click.native="handleClick(poem.id)"
        v-for="poem in poemList"
        :key="poem.id"
        :poemObj="poem"
      />
    </div>
    <transition name="jump">
      <div v-if="isShowCard" class="hidden-card" @click.self="hiddenCard">
        <horse-lamp
          class="horse-lamp"
          :poemListArr="poemList"
          :poemId="poemId"
        />
      </div>
    </transition>
  </div>
</template>

<script>
import ProductionCard from "@/components/ProductionCard";
import HorseLamp from "@/components/HorseLamp";
export default {
  name: "Production",
  components: {
    ProductionCard,
    HorseLamp,
  },
  props: {
    poemList: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      isShowCard: false,
      poemId:0,
    };
  },
  methods: {
    handleClick(id) {
      this.isShowCard = true;
      this.poemId = id*1;
    },
    hiddenCard() {
      this.isShowCard = false;
    },
  },
  mounted() {},
  destroyed() {},
};
</script>

<style lang="less" scoped>
.production {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  // padding: 40px 0px;
  box-sizing: border-box;
  .box {
    width: 70%;
    height: 50%;
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
  }
  .hidden-card {
    position: absolute;
    width: 100vw;
    height: 100vh;
    top: 0px;
    left: 0px;
    // border-radius: 7px;
    background: #f0f0f0f5;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    .horse-lamp {
      width: 700px;
      height: 400px;
      //   filter: blur(2px);
    }
  }
}

.jump-enter-active {
  animation: fadeInDownBig 1s ease;
}
.jump-leave-active {
  animation: fadeInDownBig 1s ease reverse;
}
</style>