<template>
  <div class="about-time">
    <div class="time-box">
      <h1>工作经历</h1>
      <about-time-line :timeLineList="workList"/>
    </div>
    <div class="time-box">
      <h1>教育经历</h1>
      <about-time-line :timeLineList="eduList"/>
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
  data() {
    return {
      workList: [
        {
          id: 1,
          startYear: "2017",
          endYear: "2020",
          postition: "交互设计",
          company: "加吧",
          detail:
            "您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素",
        },
        {
          id: 2,
          startYear: "2017",
          endYear: "2020",
          postition: "交互设计",
          company: "加吧",
          detail:
            "您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素",
        },
        {
          id: 3,
          startYear: "2017",
          endYear: "2020",
          postition: "交互设计",
          company: "加吧",
          detail:
            "您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素",
        },
      ],
      eduList: [
        {
          id: 1,
          startYear: "2017",
          endYear: "2020",
          postition: "交互设计",
          company: "加吧",
          detail:
            "您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素",
        },
        {
          id: 2,
          startYear: "2017",
          endYear: "2020",
          postition: "交互设计",
          company: "加吧",
          detail:
            "您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素",
        },
        {
          id: 3,
          startYear: "2017",
          endYear: "2020",
          postition: "交互设计",
          company: "加吧",
          detail:
            "您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素",
        },
      ],
    };
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