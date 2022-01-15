<template>
  <div class="box">
    <div class="info-list">
      <div class="info-list-item" v-for="info in infoList" :key="info.infoid">
        <div class="info-key">{{ info.infoName }}</div>
        <span>:</span>
        <div class="info-value">{{ info.infoValue }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutPersonInfo",
  props: {
    infoList: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      titles: {
        title: ["ABOUT", "ME"],
        describe: "我的基本信息和一些自我介绍",
      },
    };
  },
};
</script>

<style lang="less" scoped>
.box {
  .info-list {
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
    height: 500px;
    width: 550px;
    box-sizing: border-box;
    .info-list-item {
      display: flex;
      flex-flow: row;
      justify-content: flex-start;
      align-items: center;
      padding: 15px 0px;
      border-bottom: 1px #eee solid;
      text-align: left;
      width: 245px;
      height: 52px;
      div {
        text-align: left;
      }
      .info-key {
        color: #555;
      }
      .info-value {
        color: #888;
      }
    }
  }
}
</style>