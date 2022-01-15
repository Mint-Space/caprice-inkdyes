<template>
    <div class="box">
        <time-line/>
        <time-line/>
        <time-line/>
    </div>
</template>

<script>
import TimeLine from "@/components/TimeLine"
export default {
  name: "AboutTimeLine",
  components:{
      TimeLine
  }
};
</script>

<style lang="less" scoped>
.box{
    // width: 500px;
    // height: 500px;
}
</style>