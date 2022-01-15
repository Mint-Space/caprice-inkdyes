<template>
  <div class="time-line-box">
    <div class="box-left">
      <span class="time-line-cicle"></span>
      <div class="time-line-vertical-line"></div>
    </div>
    <div class="box-right">
      <div class="date">2017-2019</div>
      <div class="title">交互设计 - <span>华为</span></div>
      <div class="describe">
        您可以双击这里或者点击编辑按钮来修改内容。您还可以添加图标，按钮，图片等常用元素
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TimeLine",
};
</script>

<style lang="less" scoped>
.time-line-box {
  height: 150px;
  display: flex;
  flex-flow: row;
  justify-content: flex-start;
  //   align-items: center;
  .box-left {
    display: flex;
    flex-flow: column;
    justify-content: flex-start;
    align-items: center;
    padding-right: 30px;
    .time-line-cicle {
      width: 10px;
      height: 10px;
      border-radius: 10px;
      border: 2px solid #dba621;
      float: left;
    }
    .time-line-vertical-line {
      height: 100%;
      border-left: 2px solid #dba621;
    }
  }
  .box-right {
    display: flex;
    flex-flow: column;
    justify-content: space-around;
    align-items: flex-start;
    width: 450px;
    .date {
      display: flex;
      flex-flow: row;
      justify-content: flex-start;
      align-items: center;
      font-size: 13px;
      height: 34px;
      color: #888;
      padding-top: 5px;
    }
    .title {
      display: flex;
      flex-flow: row;
      justify-content: flex-start;
      align-items: center;
      font-size: 18px;
      color: #555;
      height: 63px;
      span {
        font-weight: bolder;
      }
    }
    .describe {
      display: flex;
      flex-flow: row;
      justify-content: flex-start;
      align-items: center;
      text-align: left;
      font-size: 14px;
      color: #888;
      height: 88px;
      padding-bottom: 20px;
    }
  }
}
</style>