<template>
  <div class="home">
    <div class="top_bg">
      <img src="/img/top_bg.jpg" />
    </div>

    <div class="inner">
      <div class="top">
        <h2>세탁기</h2>
        <div class="state-box">
          <dl class="stop">
            <dt>
              <span></span>
              <label>대기중</label>
            </dt>
            <dd>0</dd>
          </dl>
          <dl class="play">
            <dt>
              <span></span>
              <label>동작중</label>
            </dt>
            <dd>0</dd>
          </dl>
        </div>
      </div>

      <div class="guide">
        <v-icon size="18" class="mr-2">mdi-message-outline</v-icon>세탁물의 양에
        따라 동작시간이 달라질 수 있습니다
      </div>

      <div class="reload-info">
        <div class="time">
          <label>마지막갱신시간</label>
          <span>06.18 15:13</span>
        </div>

        <v-btn text plain>
          갱신하기
        </v-btn>
      </div>      


      <div class="eq_list">
        <v-row>
          <v-col cols="12" sm="6" md="4">
            <div class="item">
              <div class="item-head">
                <span class="stop">대기중</span>
                <strong>1번 초강력 세탁기</strong>
              </div>
              <div class="item-body">
                <div class="left">
                  <span class="weight">24kg</span>
                  <strong>
                    <img src="@/assets/img/stop.png" />
                  </strong>
                </div>
                <div class="right">
                  <label>대기중</label>
                </div>
              </div>
            </div>
          </v-col>

          <v-col cols="12" sm="6" md="4">
            <div class="item">
              <div class="item-head">
                <span class="play">동작중</span>
                <strong>1번 초강력 세탁기</strong>
              </div>
              <div class="item-body">
                <div class="left">
                  <span class="weight">24kg</span>
                  <strong><img src="@/assets/img/play.gif" /></strong>
                </div>
                <div class="right">
                  <span>남은시간</span>
                  <strong>34</strong>
                </div>
              </div>
            </div>
          </v-col>

          <v-col cols="12" sm="6" md="4">
            <div class="item">
              <div class="item-head">
                <span class="play">동작중</span>
                <strong>1번 초강력 건조기</strong>
              </div>
              <div class="item-body">
                <div class="left">
                  <span class="weight">24kg</span>
                  <strong><img src="@/assets/img/play-hot.gif" /></strong>
                </div>
                <div class="right">
                  <span>남은시간</span>
                  <strong>34</strong>
                </div>
              </div>
            </div>
          </v-col>
        </v-row>
      </div>
    </div>
    <!-- inner -->
  </div>
</template>

<script>
export default {
  name: "Home",

  data() {
    return {
      tabActive: 0,
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  background:#f8f8f8;

  .top_bg {
    position: absolute;
    top: 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 200px;
    overflow: hidden;
    background:#393939;

    img {
      width: 120%;
      height: auto;
      filter: blur(1px) opacity(0.15);
    }
  }

  .inner {
    position: relative;
    z-index: 2;
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    transition: padding 1s;
  }

  .top {
  
    h2{
      font-size:32px;
      color:#fff;
      height:150px;
      display:flex;
      justify-content: center;
      align-items: center;
      transition:height 0.5s
    }

    .state-box {
      display: flex;
      align-items: center;
      border: 1px solid #e2e2e2;
      border-radius: 5px;
      overflow: hidden;
      background: #fff;

      dl {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        border-right: 1px solid #e2e2e2;
        flex: 1;
        padding: 15px;
        height: 100px;

        dt {
          display: flex;
          align-items: center;

          span {
            display: inline-block;
            width: 10px;
            height: 10px;
            background: #e2e2e2;
            margin-right: 8px;
            border-radius: 3px;
          }
          label {
            font-size: 14px;
            line-height: 14px;
          }
        }

        dd {
          text-align: right;
          font-size: 32px;
          font-weight: 500;
          line-height: 32px;
        }
      }
      dl:last-child {
        border-right: 0px;
      }
      dl.play {
        dt {
          span {
            background: #1f96d1;
          }
        }
        dd {
          color: #1f96d1;
        }
      }
      dl.stop {
        dt {
          span {
            background: #eb0973;
          }
        }
        dd {
          color: #eb0973;
        }
      }
      
    }
  }

  .reload-info{
    display:flex;
    justify-content: space-between;
    align-items:center;
    margin-top:30px;
    border-bottom:1px solid #e2e2e2;
    margin-bottom:24px;
    padding-bottom:10px;

    .time{
      label{color:#888;font-size:12px;margin-right:10px;}
      span{
        color:#292929;
      }
    }

    .v-btn{
      border:1px solid #292929;
      color:#292929;
      height:26px;
      padding:0px 15px;
      font-size:12px;
      letter-spacing: 0;
    }
  }

  .guide {
    margin-top: 15px;
    background: #fee5e5;
    padding: 10px;
    border-radius: 3px;
    font-size: 12px;

    .v-icon {
      color: #eb0973;
    }
  }

  .eq_list {
    padding-bottom: 60px;
  }

  .item {
    border: 1px solid #e2e2e2;
    background:#fff;
    border-radius:5px;
    overflow:hidden;
    box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.05);
    .item-head {
      display: flex;
      align-items: center;
      padding: 0 10px;
      height: 40px;
      border-bottom: 1px solid #e2e2e2;
      span {
        font-size: 11px;
        line-height: 11px;
        background: #292929;
        color: #fff;
        border-radius: 3px;
        padding: 5px;
        margin-right: 10px;
      }
      strong {
        font-weight: normal;
      }

      span.stop {
        background: #eb0973;
      }
      span.play {
        background: #1f96d1;
      }
    }
    .item-body {
      display: flex;
      min-height: 120px;
      padding: 15px;

      .left {
        display: flex;
        width: 100px;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        border-right: 1px solid #e2e2e2;
        padding-right: 20px;

        span {
          display: block;
          color: #079f6c;
        }
        strong {
          display: block;
          img{
            height:70px;
          }
        }
      }
      .right {
        flex: 1;
        display: flex;
        align-items: flex-end;
        justify-content: flex-end;
        padding-left: 20px;

        span {
          color: #888;
          font-size: 12px;
          margin-right: 10px;
        }
        strong {
          font-size: 42px;
          line-height: 42px;
        }
        strong:after {
          content: "분";
          font-size: 14px;
          line-height: 14px;
          font-weight: 400;
          margin-left: 10px;
        }

        label{
          font-size:28px;
          font-weight:600;
        }
      }
    }
  }
}

@media screen and(max-width:1200px) {
  .inner {
    padding: 0 20px;

    .top {
      h2 {
        height: 120px;
        transition: height 1s;
      }
    }
  }
}
</style>
