<template>
  <div class="container">
    <transition name="title-into">
      <titles class="container-title" :titles="titles" v-show="isTitle"/>
    </transition>
    <div class="container-body">
      <transition-group name="contact-into" tag="div" class="box">
        <contact-info key="1" v-show="isContact" />
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
      titles: {
        title: ["CONTACT", "ME"],
        describe: "您可以随时联系我",
      },
    };
  },
  methods: {
    isShow() {
      setTimeout(() => {
        this.isContact = true;
      }, 150);
      this.isTitle = true;
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