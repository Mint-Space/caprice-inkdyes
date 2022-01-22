<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" :titles="titles" v-show="isTitle" />
    </transition>
    <div class="container-box">
      <transition-group name="info-into">
        <div class="box-line" key="1" v-show="isInfo">
          <about-person-image />
          <about-person-info class="container-info" :infoList="infoList" />
        </div>
        <box-line key="2" v-show="isInfo" />
      </transition-group>
    </div>
    <div class="container-box">
      <transition name="time-into">
        <about-time v-show="isTime" />
      </transition>
    </div>
    <div class="container-box">
      <transition name="skill-into">
        <about-skill v-show="isSkill" />
      </transition>
    </div>
  </div>
</template>

<script>
import "animate.css";
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
      isTitle: false,
      isInfo: false,
      isTime: false,
      isSkill: false,
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
  methods: {
    isShow() {
      this.isTitle = true;
      setTimeout(() => {
        this.isInfo = true;
        this.isTime = true;
        this.isSkill = true;
      }, 150);
    },
  },
  mounted() {
    this.isShow();
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
    height: 30vh;
  }
  .container-box {
    display: flex;
    flex-flow: column;
    width: 66%;
    .box-line {
      display: flex;
      flex-flow: row;
      justify-content: space-between;
      align-items: center;
      .container-info {
        height: 70vh;
        display: flex;
        flex-flow: row;
        align-items: center;
      }
    }
  }
}
.title-into-enter-active,
.info-into-enter-active,
.time-into-enter-active,
.skill-into-enter-active {
  animation: fadeInRightBig 1s;
}
</style>