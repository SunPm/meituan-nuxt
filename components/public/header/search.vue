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
          v-model="searchText"
          class="search-text"
          type="text" 
          placeholder="搜索商家或地点"
          @focus="searchFocus = true"
          @blur="searchBlur"
          @input="inputChange">
        <i class="el-icon-search search-btn" />
        <div 
          v-show="searchFocus"
          class="hot-search" >
          <p class="hot-search-title">热门搜索</p>
          <p class="hot-search-options">
            <nuxt-link
              to="/b"
            >
              北京欢乐谷
            </nuxt-link>
            <nuxt-link
              to="/"
            >
              故宫博物院
            </nuxt-link>
          </p>
        </div>
        <div 
          v-show="searchFocus&&searchText"
          class="search-list">
          <p 
            v-for="(item, index) in searchInfo"
            :key="index">
            <nuxt-link
              to="/"
            >
              {{ item }}
            </nuxt-link>
          </p>
        </div>
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
export default {
  data() {
    return {
      searchFocus: false,
      searchText: '',
      searchInfo: ['火锅A', '火锅B', '火锅C']
    }
  },
  methods: {
    searchBlur() {
      setTimeout(() => {
        this.searchFocus = false
      }, 200)
    },
    inputChange() {
      console.log(this.searchText)
    }
  }
}
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
      .hot-search {
        position: absolute;
        width: 437px;
        background: #fff;
        border-radius: 0 0 5px 5px;
        padding: 20px 15px 20px 10px;
        z-index: 5;
        font-size: 12px;
        color: #999;
        box-shadow: 0 5px 3px 0 rgba(0, 0, 0, 0.1);
        .hot-search-title {
          font-weight: bold;
          margin-bottom: 15px;
        }
        .hot-search-options {
          a {
            color: #999;
            text-decoration: none;
            margin-right: 5px;
            &:hover {
              color: #13d1be;
            }
          }
        }
      }
      .search-list {
        position: absolute;
        width: 462px;
        background: #fff;
        border-radius: 0 0 5px 5px;
        padding-top: 5px;
        z-index: 7;
        box-shadow: 0 5px 7px 0 rgba(0, 0, 0, 0.1);
        p {
          padding: 0 10px;
          line-height: 26px;
          &:hover {
            background: rgb(248, 248, 248);
            a {
              color: #13d1be;
            }
          }
          a {
            text-decoration: none;
            font-size: 12px;
          }
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
