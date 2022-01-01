<template>
  <div class="container">
    <titles class="container-title" :titles="titles" />
  </div>
</template>

<script>
import Titles from "@/components/Title";

export default {
  name: "Blog",
  components: {
    Titles,
  },
  data() {
    return {
      titles: {
        title: ["BL", "OG"],
        describe: "有关网页设计和开发的技巧",
      },
    };
  },
};
</script>

<style lang="less" scoped>
</style>