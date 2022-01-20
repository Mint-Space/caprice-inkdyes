<template>
  <div class="about-skill">
    <h1>技能介绍</h1>
    <div class="about-skill-list">
      <box-skill v-for="(progressObjs,id) in skillList" :key="id" :progress-obj="progressObjs"/>
    </div>
  </div>
</template>

<script>
import BoxSkill from "@/components/BoxSkill";
export default {
  name: "AboutSkill",
  data(){
    return{
      skillList:[
        {
          id:1,
          progressTitle:"吃饭",
          progressPercent:"50%"
        },
        {
          id:2,
          progressTitle:"树胶",
          progressPercent:"70%"
        },
        {
          id:3,
          progressTitle:"年后",
          progressPercent:"60%"
        },
        {
          id:4,
          progressTitle:"发放",
          progressPercent:"80%"
        },
        {
          id:5,
          progressTitle:"沙发落后发",
          progressPercent:"20%"
        },
        {
          id:6,
          progressTitle:"沙后发",
          progressPercent:"20%"
        },
      ]
    }
  },
  components: {
    BoxSkill,
  },
};
</script>

<style lang="less" scoped>
.about-skill{
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    align-items: flex-start;
    margin-top: 120px;
    width: 100%;
    margin-bottom: 120px;
    h1{
        padding-bottom: 75px;
    }
    .about-skill-list{
        display: flex;
        flex-flow: row;
        justify-content: space-between;
        align-items: flex-start;
        flex-wrap: wrap;
        width: 100%;
    }
}
</style>