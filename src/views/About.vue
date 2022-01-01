<template>
  <div class="about">
    <div class="about-info-head">
      <section class="section-info">
        <div class="about-title">
          <h1 class="head-title">ABOUT ME</h1>
          <div class="head-desic">
            <div class="head-desic-color"></div>
            <h3 class="head-desic-title">我的基本信息和一些自我介绍</h3>
            <div class="head-desic-color"></div>
          </div>
        </div>

        <div class="about-info-body">
          <div class="info-body-container">
            <div class="info-body-container-left">
              <div>
                <img src="../assets/logo.png" alt="" srcset="" />
              </div>
            </div>
            <div class="info-body-container-right">
              <div class="info-list">
                <div
                  class="info-list-item"
                  v-for="info in infoList"
                  :key="info.infoid"
                >
                  <div class="info-list-item-key">{{ info.infoName }}</div>
                  <span>:</span>
                  <div class="info-list-item-value">{{ info.infoValue }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  data() {
    return {
      infoList: [
        {
          infoid: 1,
          infoName: "出生日期",
          infoValue: "1988/11/05",
        },
        {
          infoid: 2,
          infoName: "名族",
          infoValue: "汉族",
        },
        {
          infoid: 3,
          infoName: "毕业院校",
          infoValue: "北京大学",
        },
        {
          infoid: 5,
          infoName: "籍贯",
          infoValue: "中国北京",
        },
        {
          infoid: 6,
          infoName: "英文名",
          infoValue: "LILI LIU",
        },
        {
          infoid: 7,
          infoName: "手机",
          infoValue: "18555555555",
        },
        {
          infoid: 8,
          infoName: "邮箱",
          infoValue: "lililiu@email.com",
        },
        {
          infoid: 9,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
        {
          infoid: 10,
          infoName: "英文名",
          infoValue: "LILI LIU",
        },
        {
          infoid: 11,
          infoName: "手机",
          infoValue: "18555555555",
        },
        {
          infoid: 12,
          infoName: "邮箱",
          infoValue: "lililiu@email.com",
        },
        {
          infoid: 13,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
        {
          infoid: 14,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
      ],
    };
  },
};
</script>

<style lang="less" scoped>
.section-info{
  width: 100%;
  height: 100%;
}
.about-title {
  width: 100%;
  height: 20%;
  .head-desic {
    position: relative;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    .head-desic-color {
      width: 50px;
      height: 2px;
      background-color: #dba621;
    }
    .head-desic-title {
      padding: 10px 20px;
    }
  }
}

.about-info-body {
  width: 100%;
  height: 80%;
  .info-body-container {
    width: 100%;
    height: 100%;
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    .info-body-container-left {
      position: relative;
      width: 50%;
      height: 80%;
      display: flex;
      flex-flow: row;
      justify-content: center;
      align-items: center;
      div {
        position: relative;
      }
      div:after {
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
    // .info-body-container-left:after {
    //   position: absolute;
    //   content: "";
    //   top: 10px;
    //   left: 10px;
    //   width: 50%;
    //   height: 80%;
    //   border: 5px solid #dba621;
    // }
    .info-body-container-right {
      width: 50%;
      height: 80%;
      padding: 30px;
      .info-list {
        display: flex;
        flex-flow: column;
        justify-content: flex-start;
        flex-wrap: wrap;
        height: 60vh;
        .info-list-item {
          display: flex;
          flex-flow: row;
          justify-content: flex-start;
          align-items: center;
          padding: 20px 50px;
          .info-list-item-key {
            text-align: left;
            border-bottom: 1px #333 solid;
          }
          .info-list-item-value {
            text-align: left;
            border-bottom: 1px #333 solid;
          }
        }
      }
    }
  }
}
</style>