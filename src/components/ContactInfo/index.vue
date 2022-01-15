<template>
  <div class="contact">
    <div class="contact-info">
      <contact-info-item />
      <contact-info-item />
      <contact-info-item />
      <contact-info-item />
      <contact-info-item />
    </div>
    <div class="contact-icon">
      <img src="../../assets/logo.png" alt="" srcset="" />
      <img src="../../assets/logo.png" alt="" srcset="" />
      <img src="../../assets/logo.png" alt="" srcset="" />
      <img src="../../assets/logo.png" alt="" srcset="" />
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
};
</script>

<style lang="less" scoped>
.contact {
  display: flex;
  flex-flow: column;
  justify-content: center;
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
    img {
      width: 30px;
      height: 30px;
      padding-right: 20px;
    }
  }
}
</style>