<template>
  <div class="info-list">
    <div class="info-title">电话</div>
    <div class="info-item">
      <span class="info-icon"></span>
      <div class="info-message">+86 13216285978</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactInfoItem",
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
    }
    .info-message {
    }
  }
}
</style>