<template>
  <div class="box">
    <div class="img">
      <img src="@/assets/logo.png" alt="me" srcset="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutPersonImage",
};
</script>

<style lang="less" scoped>
.box {
    height: 100%;
    width: 100%;
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  .img {
    position: relative;
  }
  .img:after {
    position: absolute;
    content: "";
    top: 20px;
    left: 20px;
    width: 100%;
    height: 100%;
    border: 5px solid #dba621;
    z-index: -1;
  }
}
</style>