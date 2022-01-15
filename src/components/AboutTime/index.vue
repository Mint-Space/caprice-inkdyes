<template>
  <div class="about-time">
    <div class="time-box">
      <h1>工作经历</h1>
      <about-time-line />
    </div>
    <div class="time-box">
      <h1>教育经历</h1>
      <about-time-line />
    </div>
  </div>
</template>

<script>
import AboutTimeLine from "@/components/AboutTimeLine";
export default {
  name: "AboutTime",
  components: {
    AboutTimeLine,
  },
};
</script>

<style lang="less" scoped>
.about-time {
  margin-top: 100px;
  width: 100%;
  display: flex;
  flex-flow: row;
  justify-content: space-between;
  align-items: center;
  .time-box {
    text-align: left;
    h1 {
      padding: 75px 0px;
    }
  }
}
</style>