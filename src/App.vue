<template>
  <div id="app">
    <div class="nav">
      <div>
        <img alt="Vue logo" src="./assets/logo.png" />
      </div>
      <div class="nav-list">
        <div class="link" v-for="link in links" :key="link.id">
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
export default {
  name: "App",
  data() {
    return {
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
          linkPath: "/samplereels",
          linkName: "SampleReels",
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
  }
}
* {
  margin: 0px;
  padding: 0px;
}
</style>
