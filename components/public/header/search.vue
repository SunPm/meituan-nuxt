<template>
  <div class="m-search">
    <div class="left">
      <div class="left-top">
        <nuxt-link
          to="/"
        >
          <img src="../../../assets/img/meituan.png">
        </nuxt-link>
      </div>
      <div class="left-bottom">
        <span>全部分类</span>
      </div>
    </div>
    <div class="right">
      <div class="right-top">
        <input 
          class="search-text"
          type="text" 
          placeholder="搜索商家或地点">
        <i class="el-icon-search search-btn" />
      </div>
      <div class="right-mid">
        <nuxt-link
          to="/"
        >
          北京欢乐谷
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          故宫博物院
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          青山公园
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          八达岭长城
        </nuxt-link>
      </div>
      <div class="right-bottom">
        <nuxt-link
          to="/"
        >
          美团外卖
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          猫眼电影
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          美团酒店
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          民宿/公寓
        </nuxt-link>
        <nuxt-link
          to="/"
        >
          商家入驻
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.m-search {
  .left {
    display: inline-block;
    .left-top {
      padding: 28px 60px 40px 0;
      img {
        width: 126px;
        height: 46px;
      }
    }
    .left-bottom {
      height: 50px;
      padding: 15px 0 0 15px;
      box-sizing: border-box;
      width: 230px;
      color: #fff;
      background: rgb(40, 190, 172);
    }
  }
  .right {
    display: inline-block;
    padding-top: 28px;
    vertical-align: top;
    margin-left: 60px;
    .right-top {
      .search-text {
        box-sizing: border-box;
        outline: none;
        width: 462px;
        height: 40px;
        padding: 10px;
        border: 1px solid #13d1be;
        border-radius: 5px 0 0 5px;
        &::placeholder {
          color: #999;
        }
      }
      .search-btn {
        position: relative;
        color: #fff;
        padding: 12px 35px 13px 35px;
        background: #13d1be;
        border-radius: 0 5px 5px 0;
        left: -5px;
        top: 1px;
        cursor: pointer;
      }
    }
    .right-mid {
      padding: 10px;
      a {
        font-size: 12px;
        text-decoration: none;
        color: #999;
        margin-right: 5px;
        &:hover {
          color: #13d1be;
        }
      }
    }
    .right-bottom {
      margin-top: 25px;
      a {
        color: black;
        font-weight: bold;
        margin-right: 40px;
        text-decoration: none;
        &:hover:nth-child(1) {
          color: rgb(251, 199, 0);
        }
        &:hover:nth-child(2) {
          color: rgb(237, 10, 100);
        }
        &:hover:nth-child(3) {
          color: rgb(237, 10, 100);
        }
        &:hover:nth-child(4) {
          color: rgb(251, 199, 0);
        }
        &:hover:nth-child(5) {
          color: #13d1be;
        }
      }
    }
  }
}
</style>
