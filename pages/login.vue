<template>
  <div>
    <div>
      <label>用户名</label>
      <input 
        v-model="username"
        type="text" 
      >
    </div>
    <div>
      <label>密码</label>
      <input 
        v-model="password"
        type="text">
    </div>
    <div>
      <button @click="login">登录</button>
    </div>
  </div>
</template>

<script>
import CryptoJs from 'crypto-js'
export default {
  data() {
    return {
      username: '',
      password: ''
    }
  },
  layout: 'blank',
  methods: {
    async login() {
      const { data } = await this.$axios.post('/user/signin', {
        username: this.username,
        password: CryptoJs.MD5(this.password).toString()
      })
      if (data.code === 0) {
        location.href = '/'
      }
    }
  }
}
</script>

<style scoped>
</style>
