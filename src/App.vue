<template>
  <v-app>
    <div class="header">
      <div class="logo">
        <img src="./assets/img/logo_b.png">
      </div>
      <div class="shop">
        부산대 금정점
      </div>
    </div>
    <div class="nav">
      <div class="inner">
        <v-btn 
          text
          plain
          v-for="(item, index) in ['세탁기', '건조기']" 
          :key="index"
          :class="{active:navActive === index}"
          @click="navActive = index"
        >
            {{item}}
        </v-btn>
      </div>
    </div>
    
    <router-view />

    <div class="footer">
      <div class="inner">
        <div class="logo">
          <img src="./assets/img/logo_b.png">
        </div>
        <div class="company">
          <p>세탁프리워시 금정점</p>
          <ul>
            <li>
              <label>전화</label>
              <span>010-1234-1234</span>
            </li>
            <li>
              <label>주소</label>
              <span>부산시 금정구 부산대학로 63번길 과학기술연구동 201호 페이오티</span>
            </li>
          </ul>
        </div>
        <div class="copyright">
          COPYRIGHT (C) PAYOT ALL RIGHTS RESERVED
        </div>
      </div>
    </div>
   
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    navActive: 0
  }),
};
</script>

<style lang="scss" scoped>

.header{
  display:flex;
  align-items: center;
  justify-content: space-between;
  height:60px;
  border-bottom:1px solid #e2e2e2;
  padding:0 15px;
  background:#fff;

  img{
    height:36px;
  }
}

.nav{
  position:sticky;
  top:0px;
  z-index:3;
  background:#fff;

  .inner{
    display:flex;
    align-items: center;
    justify-content: center;
  }

  .v-btn{
    flex:1;
    border-radius:0px;
    min-height:50px;
    max-width:150px;
    transition: all 0.5s;
  }
  .v-btn.active{
    color:#1f96d1;
  }
  .v-btn:after{
    position: absolute;
    bottom:0px;
    content:'';
    height:1px;
    width:100%;
    background:#e2e2e2;
  }
  .v-btn.active:after{
    position: absolute;
    bottom:0px;
    content:'';
    height:3px;
    width:100%;
    background:#1f96d1;
  }
}

.footer{
  padding:30px 0;
  background:#fff;
  border-top:1px solid #e2e2e2;
  text-align:center;
  font-size:12px;color:#888;

  .inner{
    max-width:1200px;
    padding:0 20px;
    margin:0 auto;
  }

  .logo{
    margin-bottom:15px;
    img{height:30px; filter:grayscale(0.9);}
  }
  
  .company{
    max-width:600px;
    margin:0px auto;

    p{
      color:#292929;
      text-align:center;
      margin-bottom:8px;
    }
    ul{      
      padding:0px;
      
      li{
        display:inline;
        margin-right:10px;
        margin-bottom:3px;
        font-size:11px;

        label{
          color:#292929;
          margin-right:4px;
        }
      }
      li:last-child{
        margin-right:0px;
      }
    }
  }

  .copyright{
    font-size:11px;
    margin-top:10px;
  }
}

@media screen and(max-width:1200px) {
  .nav{
    .inner{
      .v-btn{
        max-width:100%;
        transition: all 1s;
      }
    }
  }
}

</style>