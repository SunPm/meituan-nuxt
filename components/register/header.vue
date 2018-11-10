<template>
  <div class="header">
    <div class="main">
      <div>
        <nuxt-link
          to="/"
        >
          <img 
            class="logo"
            src="../../assets/img/meituan.png">
        </nuxt-link>
      </div>
      <div class="right">
        <span>已有美团帐号?</span>
        <nuxt-link
          to="/"
        >登录</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'blank'
}
</script>

<style lang="scss" scoped>
.header {
  border-bottom: 2px solid #2bb8aa;
  color: #666;
  .main {
    display: flex;
    justify-content: space-between;
    width: 980px;
    position: relative;
    margin: 0 auto;
    padding: 10px 0;
    .logo {
      width: 54px;
      height: 36px;
    }
    .right {
      line-height: 36px;
      font-size: 14px;
      a {
        font-size: 13px;
        text-decoration: none;
        margin-left: 15px;
        padding: 2px 10px 4px 10px;
        background: #2db3a6;
        color: #fff;
        font-weight: 400;
        border-radius: 2px;
      }
    }
  }
}
</style>
