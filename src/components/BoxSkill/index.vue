<template>
  <div class="progress">
    <div class="progress-box">
      <div class="progress-title">{{title}}</div>
      <div class="progress-percent">{{progress}}</div>
    </div>
    <div class="progress-bar" :style="cssVars"></div>
  </div>
</template>

<script>
export default {
  name: "BoxSkill",
  props:{
    progressObj:{
      type: Object,
      required: true
    },
    
  },
  data(){
    return{
      title:this.progressObj.progressTitle,
      progress:this.progressObj.progressPercent,
    }
  },
  computed:{
    cssVars(){
      return{
        "--progress":this.progress
      }
    }
  }
};
</script>

<style lang="less" scoped>
.progress {
  padding: 25px 0px;
  width: 30%;
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
    padding: 5px 0px;
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
    width: var(--progress);
    margin: 10px 0px;
    background-color: #dba621;
  }
}
</style>