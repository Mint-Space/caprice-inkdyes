<template>
  <div class="about-skill">
    <h1>技能介绍</h1>
    <div class="about-skill-list">
      <box-skill />
      <box-skill />
      <box-skill />
      <box-skill />
      <box-skill />
      <box-skill />
    </div>
  </div>
</template>

<script>
import BoxSkill from "@/components/BoxSkill";
export default {
  name: "AboutSkill",
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