<template>
  <div class="card-box" @mouseenter="moveIn" @mouseleave="moveOut">
    <div class="card-img" ref="cardImg">
      <img :src="blogCard.imgSrc" alt="" />
    </div>
    <transition name="card">
      <div class="card-font" ref="cardFont" v-show="isCard">
        <div class="card-font-box">
          <div class="card-title">{{blogCard.title}}</div>
          <div class="card-date">{{blogCard.date}}</div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
import "animate.css";
export default {
  name: "BlogLampCard",
  props:{
    blogCardObj:{
      type:Object,
      required:true
    }
  },
  data() {
    return {
      isCard: false,
      blogCard:this.blogCardObj
    };
  },
  methods: {
    moveIn() {
      this.isCard = true;
    },
    moveOut() {
      this.isCard = false;
    },
  },
};
</script>

<style lang="less" scoped>
.card-box {
  position: relative;
  // width: 450px;
  // height: 250px;

  .card-img {
    width: 100%;
    transition: transform 0.5s ease-out;
    transform: scale(1);
    img {
      transition: border-radius 1s ease-out;
      border-radius: 15px;
      width: 100%;
    }
  }
  .card-img:hover {
    width: 100%;
    transition: transform 0.5s ease-in;
    transform: scale(1.05);
    img {
      transition: border-radius 1s ease-in;
      border-radius: 0px;
      width: 100%;
    }
  }
  .card-font {
    display: none;
    box-sizing: border-box;
    .card-title {
      font-size: 16px;
      color: #dba621;
    }
    .card-date {
      font-size: 12px;
      color: rgb(122, 122, 122);
    }
  }
}
.card-box .card-font {
  position: absolute;
  bottom: 0px;
  left: 0px;
  width: 100%;
  height: 35%;
  background: rgba(255, 255, 255, 0.856);
  display: block;
  padding: 15px;
  box-sizing: border-box;
  .card-font-box {
    border: 1px solid #dba621;
    display: flex;
    flex-flow: column;
    justify-content: space-around;
    align-items: flex-start;
    padding: 20px;
    box-sizing: border-box;
    height: 100%;
    .card-title {
      font-size: 16px;
      color: #555;
    }
    .card-date {
      font-size: 12px;
      color: #999;
    }
  }
}
.card-enter-active {
  animation: fadeIn 1s;
}
.card-leave-active {
  animation: fadeOut 1s;
}
</style>