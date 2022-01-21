<template>
  <div class="container">
    <titles class="container-title" :titles="titles" />
    <div class="container-body">
      <blog-lamp />
    </div>
  </div>
</template>

<script>
import Titles from "@/components/Title";
import BlogLamp from "@/components/BlogLamp";
export default {
  name: "Blog",
  components: {
    Titles,
    BlogLamp,
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
.container {
  .container-title {
    height: 30vh;
  }
  .container-body {
    height: 60vh;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
}
</style>