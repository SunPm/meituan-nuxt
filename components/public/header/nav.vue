<template>
  <div class="m-nav">
    <div class="common my">
      <nuxt-link
        to="/login"
      >我的美团</nuxt-link>
      <div class="child">
        <nuxt-link
          to="/login"
        >我的订单</nuxt-link>
        <nuxt-link
          to="/login"
        >我的收藏</nuxt-link>
        <nuxt-link
          to="/login"
        >抵用券</nuxt-link>
        <nuxt-link
          to="/login"
        >帐户设置</nuxt-link>
      </div>
    </div>
    <div class="common">
      <nuxt-link
        to="/login"
      >手机APP</nuxt-link>
    </div>
    <div class="common">
      <span>商家中心</span>
    </div>
    <div class="common">
      <span>网站导航</span>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.m-nav {
  font-size: 12px;
  a {
    color: #999;
    text-decoration: none;
    &:hover {
      color: #31bbac;
    }
  }
  .common {
    padding: 0 14px;
    box-sizing: border-box;
    position: relative;
    border-left: 1px solid transparent;
    border-right: 1px solid transparent;
    height: 36px;
    line-height: 36px;
    display: inline-block;
    color: #999;
    &:hover {
      color: #31bbac;
    }
  }
  .my {
    &:hover {
      background: white;
      border-left: 1px solid #e5e5e5;
      border-right: 1px solid #e5e5e5;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      .child {
        display: block;
      }
    }
    .child {
      position: absolute;
      display: none;
      border: 1px solid #e5e5e5;
      border-top: none;
      background: #fff;
      text-align: center;
      z-index: 10;
      width: 76px;
      right: -1px;
      box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
      a {
        display: block;
      }
    }
  }
}
</style>
