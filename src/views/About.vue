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
          infoid: 4,
          infoName: "籍贯",
          infoValue: "中国北京",
        },
        {
          infoid: 5,
          infoName: "英文名",
          infoValue: "LILI LIU",
        },
        {
          infoid: 6,
          infoName: "手机",
          infoValue: "18555555555",
        },
        {
          infoid: 7,
          infoName: "邮箱",
          infoValue: "lililiu@email.com",
        },
        {
          infoid: 8,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
        {
          infoid: 9,
          infoName: "英文名",
          infoValue: "LILI LIU",
        },
        {
          infoid: 10,
          infoName: "手机",
          infoValue: "18555555555",
        },
        {
          infoid: 11,
          infoName: "邮箱",
          infoValue: "lililiu@email.com",
        },
        {
          infoid: 12,
          infoName: "现居城市",
          infoValue: "中国北京",
        },
      ],
    };
  },
};
</script>

<style lang="less" scoped>
.section-info {
  width: 100%;
  height: 100%;
}
.about-info-head {
  width: 100%;
  height: 100%;
  .about-title {
    width: 100%;
    height: 20vh;
    box-sizing: content-box;
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
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
}

.about-info-body {
  width: 100%;
  height: 80vh;
  .info-body-container {
    display: flex;
    flex-flow: row;
    justify-content: center;
    align-items: center;
    height: 100%;
    width: 100%;
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
    .info-body-container-right {
      width: 50%;
      height: 100%;
      padding: 30px 0px;
      box-sizing: border-box;
      .info-list {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: flex-start;
        flex-wrap: wrap;
        height: 90%;
        padding: 60px 0px;
        box-sizing: border-box;
        .info-list-item {
          display: flex;
          flex-flow: row;
          justify-content: flex-start;
          align-items: center;
          padding: 20px 0px;
          border-bottom: 1px #333 solid;
          text-align: left;
          width: 220px;
          height: 30px;
          .info-list-item-key {
            text-align: left;
          }
          .info-list-item-value {
            text-align: left;
          }
        }
      }
    }
  }
}
</style>