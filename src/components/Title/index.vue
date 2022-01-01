<template>
  <div class="box">
    <h1 class="title">
      {{ titles.title[0] }}&nbsp;<span>{{ titles.title[1] }}</span>
    </h1>
    <div class="describe-box">
      <div class="line-color"></div>
      <h3 class="describe">{{ titles.describe }}</h3>
      <div class="line-color"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Title",
  props: {
    titles: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="less" scoped>
.box {
  width: 100%;
  height: 100%;
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  .title {
    box-sizing: content-box;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    color: #555;
    padding: 20px 0px;
    font-size: 52px;
    span {
      color: #dba621;
    }
  }
  .describe-box {
    position: relative;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    .line-color {
      width: 35px;
      height: 2px;
      background-color: #dba621;
    }
    .describe {
      color: #333;
      padding: 0px 10px;
      font-size: 18px;
    }
  }
}
</style>