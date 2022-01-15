<template>
  <div >
    <titles :titles="titles" />
    <production />
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
</style>