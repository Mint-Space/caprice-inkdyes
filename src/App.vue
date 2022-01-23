<template>
  <div id="app">
    <div class="nav">
      <div class="me">
        <transition name="me-into">
          <img alt="Vue logo" ref="me" src="./assets/logo.png" v-show="isMe" />
        </transition>
      </div>
      <div class="nav-list">
        <div class="link" v-for="link in links" :key="link.id" @click="showMe">
          <span></span>
          <router-link :to="link.linkPath">{{ link.linkName }}</router-link>
        </div>
      </div>
    </div>
    <div class="right-container">
      <router-view />
    </div>
  </div>
</template>

<script>
import "animate.css";
export default {
  name: "App",
  data() {
    return {
      isMe: false,
      links: [
        {
          id: 1,
          linkPath: "/",
          linkName: "Home",
        },
        {
          id: 2,
          linkPath: "/about",
          linkName: "About",
        },
        {
          id: 3,
          linkPath: "/portfolio",
          linkName: "Portfolio",
        },
        {
          id: 4,
          linkPath: "/blog",
          linkName: "Blog",
        },
        {
          id: 5,
          linkPath: "/contact",
          linkName: "Contact",
        },
      ],
    };
  },
  methods: {
    showMe() {
      var animation = this.$refs.me.animate(
        [
          {
            opacity: "0",
            transform: "scale3d(0.3, 0.3, 0.3)",
          },

          {
            transform: "scale3d(1.1, 1.1, 1.1)",
          },
          {
            transform: "scale3d(0.9, 0.9, 0.9)",
          },
          {
            opacity: "1",
            transform: "scale3d(1.03, 1.03, 1.03)",
          },
          {
            transform: "scale3d(0.97, 0.97, 0.97)",
          },
          {
            opacity: "1",
            transform: "scale3d(1, 1, 1)",
          },
        ],
        {
          duration: 1000,
        }
      );
      animation.play();
    },
  },
  mounted() {
    this.isMe = true;
  },
};
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-flow: row;
  justify-content: space-between;
  align-items: center;
  height: 100vh;
  width: 100%;
  overflow: hidden;
  .nav {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    width: 10%;
    background-color: #333;
    padding: 30px;
    box-sizing: border-box;
    .me {
      width: 90px;
      height: 90px;
      overflow: hidden;
      margin-bottom: 35px;
      img {
        width: 100%;
      }
    }
    .nav-list {
      display: flex;
      flex-flow: column;
      justify-content: flex-start;
      align-items: flex-start;
      height: 60%;
      .link {
        margin: 20px 0px;
      }
    }
    a {
      font-weight: bold;
      color: #fff;
      text-decoration: none;
      &.router-link-exact-active {
        color: #dba621;
      }
    }
  }
  .right-container {
    width: 90%;
    height: 100%;
    overflow-x: hidden;
    overflow-y: scroll;
    &::-webkit-scrollbar {
      display: none; /* Chrome Safari */
      width: 0;
      // 或者 width: 0;
    }
  }
}
.me-into-enter-active {
  animation: bounceIn 1s;
}
* {
  margin: 0px;
  padding: 0px;
}
</style>
