<template>
    <div class="box">
        <time-line v-for="(timeLineObj,id) in timeLineList" :key="id" :timeLineObj="timeLineObj"/>
    </div>
</template>

<script>
import TimeLine from "@/components/TimeLine"
export default {
  name: "AboutTimeLine",
  components:{
      TimeLine
  },
  props:{
      timeLineList:{
          type:Array,
          required:true
      }
  }
};
</script>

<style lang="less" scoped>
.box{
    // width: 500px;
    // height: 500px;
}
</style>