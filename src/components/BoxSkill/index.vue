<template>
  <div class="progress">
    <div class="progress-box">
      <div class="progress-title">吃饭</div>
      <div class="progress-percent" ref="progress">{{skillPercentage}}</div>
    </div>
    <div class="progress-bar"></div>
  </div>
</template>

<script>
export default {
  name: "BoxSkill",
  data(){
    return{
      skillPercentage:"60%",
    }
  },
  mounted(){
    this.changePercentage();
  },
  methods:{
    changePercentage(){
      this.$refs.progress.style.setProperty('--progress-percentage',this.skillPercentage);
    }
  }
};
</script>

<style lang="less" scoped >
.progress {
  padding: 25px 0px;
  width: 30%;
  --progress-percentage: 20%;
  .progress-box {
    display: flex;
    flex-flow: row;
    justify-content: space-between;
    align-items: center;
    .progress-title {
      font-size: 20px;
    }
    .progress-percent {
      font-size: 25px;
      color: #dba621;
    }
  }
  .progress-bar {
    height: 3px;
    width: 100%;
    position: relative;
    margin: 10px 0px;
    padding: 10px 0px;
  }
  .progress-bar:before {
    position: absolute;
    top: 0px;
    left: 0px;
    content: "";
    height: 3px;
    width: 100%;
    margin: 10px 0px;
    background-color: #888;
  }
  .progress-bar:after {
    position: absolute;
    top: 0px;
    left: 0px;
    content: "";
    height: 3px;
    width: var(--progress-percentage);
    margin: 10px 0px;
    background-color: #dba621;
  }
}
</style>