<template>
  <div class="m-geo">
    <div class="common location">
      <i class="el-icon-location"/>北京市
    </div>
    <div class="common">
      <nuxt-link
        class="changeCity"
        to="/changeCity">切换城市</nuxt-link>
    </div>
    <div class="common">
      [<nuxt-link
        class="option"
        to="/login"
      >香河</nuxt-link>
      <nuxt-link
        class="option"
        to="/login"
      >廊坊</nuxt-link>
      <nuxt-link
        class="option"
        to="/login"
      >苍南</nuxt-link>]
    </div>
    <div 
      v-if="user"
      class="common" 
    >
      <nuxt-link
        class="login"
        to="/login"
      >{{ user }}</nuxt-link>
      <nuxt-link
        class="register"
        to="/exit"
      >退出</nuxt-link>
    </div>
    <div 
      v-else
      class="common" 
    >
      <nuxt-link
        class="login"
        to="/login"
      >立即登录</nuxt-link>
      <nuxt-link
        class="register"
        to="/register"
      >注册</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: ''
    }
  },
  async mounted() {
    try {
      const { data } = await this.$axios.get('/user/getUser')
      this.user = data.user
    } catch (error) {
      console.log(error)
    }
  }
}
</script>

<style lang="scss" scoped>
.m-geo {
  font-size: 12px;
  padding: 12px 0;
  a {
    text-decoration: none;
    &:hover {
      color: #31bbac;
    }
  }
  .common {
    display: inline-block;
    color: #999;
  }
  .location {
    color: #666;
  }
  .option {
    color: #999;
    margin: 0 5px;
  }
  .login {
    color: #31bbac;
    margin: 0 10px 0 20px;
  }
  .register {
    color: #999;
  }
  .changeCity {
    background: #f4f4f4;
    border: 1px solid #e5e5e5;
    border-radius: 2px;
    color: #666;
    margin: 0 4px;
    padding: 0 2px;
  }
}
</style>
