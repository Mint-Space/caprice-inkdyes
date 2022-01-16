<template>
  <div class="blog-lamp">
    <div class="lamp-ctrl lamp-prev" @click="prev">&lt;</div>
    <div class="blog-lamp-box">
      <div class="blog-lamp-list">
        <swiper ref="lamp" :options="swiperOptions">
          <swiper-slide
            v-for="(o, i) in 4"
            :key="i"
            class="swiper-slide swiper-zoom-container"
          >
            <div
              class="swiper-slide-zoomed swiper-zoom-target"
              @mouseenter="moveIn"
              @mouseleave="moveOut"
            >
              <img src="../../assets/sky.jpeg" alt="" srcset="" />
            </div>
          </swiper-slide>
          <!-- <div class="swiper-pagination" slot="pagination"></div> -->
        </swiper>
      </div>
    </div>
    <div class="lamp-ctrl lamp-next" @click="next">&gt;</div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";

// import style (>= Swiper 6.x)
// import "swiper/swiper-bundle.css";

// import style (<= Swiper 5.x)
import "swiper/css/swiper.css";

export default {
  name: "BlogLamp",
  components: {
    Swiper,
    SwiperSlide,
  },
  directives: {
    swiper: directive,
  },
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: ".swiper-pagination",
        },
        slidesPerView: 2,
        parallax: true,
        loop: true,
        speed: 1500,
        autoplay: {
          delay: 3000,
        },
        spaceBetween: 50,
        centeredSlidesBounds: true,
        zoom: {
          maxRatio: 1.1, //全部设置5倍
          toggle: false,
          zoomedSlideClass: "swiper-slide-zoomed",
        },
        // Some Swiper option/callback...
      },
    };
  },
  computed: {
    swiper() {
      return this.$refs.lamp.$swiper;
    },
  },
  mounted() {
    console.log("Current Swiper instance object", this.swiper);
    // this.swiper.slideTo(3, 1000, false);
  },

  methods: {
    moveIn() {
      this.$refs.lamp.$swiper.autoplay.stop();
      // console.log(this);
      this.className = "zoom-in";
      // this.$refs.lamp.$swiper.zoom.in();
    },
    moveOut() {
      this.$refs.lamp.$swiper.autoplay.start();
      this.className = "zoom-out";
      // this.swiper.zoom.out();
      // this.$refs.lamp.$swiper.zoom.out();
    },
    prev() {
      this.swiper.slidePrev();
    },
    next() {
      this.swiper.slideNext();
    },
  },
};
</script>

<style lang="less" scoped>
.blog-lamp {
  display: flex;
  flex-flow: row;
  justify-content: center;
  align-items: center;
  margin-top: 150px;
  .lamp-prev {
    margin-right: 15px;
  }
  .lamp-next {
    margin-left: 15px;
  }
  .lamp-ctrl {
    width: 40px;
    height: 40px;
    background-color: #ccc;
    font-size: 25px;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
  .lamp-ctrl:hover {
    width: 40px;
    height: 40px;
    background-color: rgb(145, 145, 145);
    font-size: 25px;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
  }
  .blog-lamp-box {
    position: relative;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    .blog-lamp-list {
      display: flex;
      flex-flow: row;
      position: relative;
      width: 1000px;
      height: 350px;
      border-radius: 15px;
      overflow: hidden;
      .swiper-slide {
        width: 50%; /*设为固定值*/
        .swiper-slide-zoomed {
          width: auto; /*根据内容调整宽度*/
          overflow: hidden;
          img {
            width: 100%;
            border-radius: 15px;
          }
        }
      }
    }
  }
}

.zoom-in {
  animation: zoom 3s ease;
}
.zoom-out {
  animation: zoom 3s ease reverse;
}
@keyframes zoom {
  from {
    transform: scale(1);
  }
  to {
    transform: scale(1.1);
  }
}
</style>