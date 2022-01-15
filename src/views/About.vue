<template>
  <div class="container">
    <titles class="container-title" :titles="titles" />
    <div class="container-box">
      <div class="box-line">
        <about-person-image />
        <about-person-info class="container-info" :infoList="infoList" />
      </div>
      <box-line />
    </div>
    <div class="container-box">
      <about-time />
    </div>
    <div class="container-box">
      <about-skill/>
    </div>
  </div>
</template>

<script>
import Titles from "@/components/Title";
import AboutPersonImage from "@/components/AboutPersonImage";
import AboutPersonInfo from "@/components/AboutPersonInfo";
import BoxLine from "@/components/BoxLine";
import AboutTime from "@/components/AboutTime";
import AboutSkill from "@/components/AboutSkill";
export default {
  name: "About",
  components: {
    Titles,
    AboutPersonImage,
    AboutPersonInfo,
    AboutTime,
    AboutSkill,
    BoxLine,
  },
  data() {
    return {
      titles: {
        title: ["ABOUT", "ME"],
        describe: "我的基本信息和一些自我介绍",
      },
      infoList: [
        {
          infoid: 1,
          infoName: "出生日期",
          infoValue: "1988/11/05",
        },
        {
          infoid: 2,
          infoName: "名族",
          infoValue: "汉族",
        },
        {
          infoid: 3,
          infoName: "毕业院校",
          infoValue: "北京大学",
        },
        {
          infoid: 4,
          infoName: "籍贯",
          infoValue: "中国北京",
        },
        {
          infoid: 5,
          infoName: "英文名",
          infoValue: "LILI LIU",
        },
        {
          infoid: 6,
          infoName: "手机",
          infoValue: "18555555555",
        },
        {
          infoid: 7,
          infoName: "邮箱",
          infoValue: "lililiu@email.com",
        },
        {
          infoid: 8,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
        {
          infoid: 9,
          infoName: "英文名",
          infoValue: "LILI LIU",
        },
        {
          infoid: 10,
          infoName: "手机",
          infoValue: "18555555555",
        },
        {
          infoid: 11,
          infoName: "邮箱",
          infoValue: "lililiu@email.com",
        },
        {
          infoid: 12,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
      ],
    };
  },
};
</script>

<style lang="less" scoped>
.container {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  .container-title {
    height: 25%;
  }
  .container-box {
    display: flex;
    flex-flow: column;
    height: 75%;
    width: 66%;
    .box-line {
      display: flex;
      flex-flow: row;
      justify-content: space-between;
      align-items: center;
      .container-info {
        height: 70vh;
        padding: 90px 0px;
        display: flex;
        flex-flow: row;
        align-items: center;
      }
    }
  }
}
</style>