<template>
  <div class="container">
    <titles class="container-title" :titles="titles" />
    <div class="container-body">
      <production />
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
      titles: {
        title: ["MY", "PROTFOLIO"],
        describe: "我的往期作品展示",
      },
    };
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
</style>