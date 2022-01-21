<template>
  <div class="contact">
    <div class="contact-info">
      <contact-info-item
        v-for="(contactObj, id) in contactInfoList"
        :key="id"
        :contactInfo="contactObj"
      />
    </div>
    <div class="contact-icon">
      <span
        :style="cssVars"
        :class="contactImgObj.icon"
        :alt="contactImgObj.title"
        v-for="(contactImgObj, id) in contactImgList"
        :key="id"
      ></span>
    </div>
  </div>
</template>

<script>
import ContactInfoItem from "@/components/ContactInfoItem";
export default {
  name: "ContactInfo",
  components: {
    ContactInfoItem,
  },
  data() {
    return {
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
    };
  },
  computed: {
    cssVars() {
      return {
        "--icon-src": "url(" + this.contactImgList[0].imgSrc + ")",
      };
    },
  },
};
</script>

<style lang="less" scoped>
.contact {
  display: flex;
  flex-flow: column;
  justify-content: space-between;
  align-items: flex-start;
  height: 80%;
  .contact-info {
    display: flex;
    flex-flow: column;
    justify-content: flex-start;
    align-items: flex-start;
    padding: 15px 0px;
  }
  .contact-icon {
    span {
      display: inline-block;
      margin-right: 20px;
      margin-bottom: 0px;
      background-image: var(--icon-src);
      width: 32px;
      height: 32px;
    }
    .video-icon_32x32 {
      background-position: -160px 0;
    }
    .qq-icon_32x32 {
      background-position: -64px 0;
    }
    .qfy-icon_32x32.corner {
      background-position-y: -32px;
    }
    .weibo-icon_32x32 {
      background-position: -32px 0;
    }
  }
}
</style>