<template>
  <div>
    <titles :titles="titles" />
  </div>
</template>

<script>
import Titles from "@/components/Title";
export default {
  name: "Portfolio",
  components: {
    Titles,
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