<template>
  <div class="info-list">
    <div class="info-title">{{ infoTitle }}</div>
    <div class="info-item">
      <i :class="`info-icon iconfont ${infoIcon}`"></i>
      <div class="info-message">{{ infoMessage }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactInfoItem",
  props: {
    contactInfo: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      infoTitle: this.contactInfo.title,
      infoIcon: this.contactInfo.icon,
      infoMessage: this.contactInfo.message,
    };
  },
};
</script>

<style lang="less" scoped>
.info-list {
  font-size: 16px;
  display: flex;
  flex-flow: column;
  justify-content: space-around;
  align-items: flex-start;
  padding: 15px 0px;
  .info-title {
    text-align: left;
    padding: 8px 0px;
  }
  .info-item {
    display: flex;
    flex-flow: row;
    justify-content: space-around;
    align-items: center;

    .info-icon {
      margin-right: 20px;
      font-size: 30px;
    }
    .info-message {
    }
  }
}
</style>