<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" :titles="titles" v-show="isTitle" />
    </transition>
    <div class="container-body">
      <transition-group name="contact-into" tag="div" class="box">
        <contact-info
          key="1"
          v-show="isContact"
          :contactInfoObj="contactInfoObj"
        />
        <div class="middle-box" key="2" v-show="isContact"></div>
        <contact-submit key="3" v-show="isContact" />
      </transition-group>
    </div>
  </div>
</template>

<script>
import "animate.css";
import Titles from "@/components/Title";
import ContactInfo from "@/components/ContactInfo";
import ContactSubmit from "@/components/ContactSubmit";
export default {
  name: "Contact",
  components: {
    Titles,
    ContactInfo,
    ContactSubmit,
  },
  data() {
    return {
      isTitle: false,
      isContact: false,
      timer: 0,
      titles: {
        title: ["CONTACT", "ME"],
        describe: "您可以随时联系我",
      },
      contactInfoObj: {
        contactInfoList: [
          {
            id: 1,
            title: "电话",
            icon: "icon",
            message: "+86 132 1628 5978",
          },
          {
            id: 2,
            title: "邮箱",
            icon: "icon",
            message: "qifeiye@admin.com",
          },
          {
            id: 3,
            title: "传真",
            icon: "icon",
            message: "+0086 5566 6857",
          },
          {
            id: 4,
            title: "地址",
            icon: "icon",
            message: "苏州市中新大道加成大厦",
          },
        ],
        contactImgList: [
          {
            id: 1,
            imgSrc:
              "https://f.goodq.top/FeiEditor/images/icon/social_icon_32x32.png",
            icon: "corner qfy-icon qfy-icon_32x32 weibo-icon_32x32",
            title: "按时发大水",
            link: "",
          },
          {
            id: 2,
            imgSrc:
              "https://f.goodq.top/FeiEditor/images/icon/social_icon_32x32.png",
            icon: "corner qfy-icon qfy-icon_32x32 weixin-icon_32x32",
            title: "是否",
            link: "",
          },
          {
            id: 3,
            imgSrc:
              "https://f.goodq.top/FeiEditor/images/icon/social_icon_32x32.png",
            icon: "corner qfy-icon qfy-icon_32x32 qq-icon_32x32",
            title: "半个坏习惯",
            link: "",
          },
          {
            id: 4,
            imgSrc:
              "https://f.goodq.top/FeiEditor/images/icon/social_icon_32x32.png",
            icon: "corner qfy-icon qfy-icon_32x32 video-icon_32x32",
            title: "水电费",
            link: "",
          },
        ],
      },
    };
  },
  methods: {
    isShow() {
      this.isTitle = true;
      this.timer = setTimeout(() => {
        this.isContact = true;
      }, 150);
    },
  },
  mounted() {
    this.isShow();
  },
  beforeDestroy() {
    clearTimeout(this.timer);
    this.isTitle = false;
    this.isContact = false;
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
  .container-body {
    height: 70vh;
    width: 100%;
    display: flex;
    flex-flow: row;
    justify-content: flex-end;
    .box {
      height: 100%;
      width: 100%;
      display: flex;
      flex-flow: row;
      justify-content: flex-end;
      .middle-box {
        width: 150px;
        height: 100%;
      }
    }
  }
}
.title-into-enter-active,
.contact-into-enter-active {
  animation: fadeInRightBig 1s;
}
</style>