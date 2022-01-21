<template>
  <div class="container">
    <titles class="container-title" :titles="titles" />
    <div class="container-body">
      <contact-info/>
      <div class="middle-box"></div>
      <contact-submit/>
    </div>
  </div>
</template>

<script>
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
      titles: {
        title: ["CONTACT", "ME"],
        describe: "您可以随时联系我",
      },
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
    height: 30vh;
  }
  .container-body {
    height: 70vh;
    width: 100%;
    display: flex;
    flex-flow: row;
    justify-content: flex-end;
    .middle-box{
      width: 150px;
      height: 100%;
    }
  }
}
</style>