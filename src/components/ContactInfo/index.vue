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
  props: {
    contactInfoObj: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      contactInfoList: this.contactInfoObj.contactInfoList,
      contactImgList: this.contactInfoObj.contactImgList,
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