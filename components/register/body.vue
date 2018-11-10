<template>
  <div class="body">
    <div class="form">
      <div class="item">
        <label class="intro">用户名</label>
        <input
          v-model="username"
          type="text"
          @focus="getPhoneFocus"
          @blur="phoneBlur">
      </div>
      <div class="item">
        <label class="intro">密码</label>
        <input
          v-model="password"
          type="text"
          @focus="getPhoneFocus"
          @blur="phoneBlur">
      </div>
      <div class="item">
        <label class="intro">邮箱号</label>
        <input
          v-model="phone"
          type="text"
          @focus="getPhoneFocus"
          @blur="phoneBlur">
        <label 
          v-if="!phoneFlag"
          class="warning">注册成功后，全美团通用</label>
        <label
          v-if="!phoneFocus&&phoneFlag"
          class="warning">
          <i class="el-icon-remove"/>
          {{ phoneWarning }}
        </label>
      </div>
      <div class="get-note">
        <button 
          :disabled="noteCount>0"
          @click="sendNote">免费获取短信动态码</button>
        <label>{{ noteCount }}秒</label>
      </div>
      <div class="item">
        <label class="intro">短信动态码</label>
        <input
          v-model="note"
          type="text"
          @focus="getPhoneFocus"
          @blur="phoneBlur">
      </div>
      <button @click="signup">注册</button>
    </div>
  </div>
</template>

<script>
import CryptoJs from 'crypto-js'
export default {
  data() {
    return {
      username: '',
      password: '',
      phone: '',
      phoneFocus: false,
      phoneFlag: false,
      phoneWarning: '',
      note: '',
      noteCount: 0
    }
  },
  methods: {
    getPhoneFocus() {
      this.phoneFlag = true
      this.phoneFocus = true
    },
    phoneBlur() {
      this.phoneFocus = false
      if (this.phone === '') {
        this.phoneWarning = '请输入您的手机号码'
      }
    },
    async sendNote() {
      let reg = /^(\w-*\.*)+@(\w-?)+(\.\w{2,})+$/
      if (reg.test(this.phone)) {
        const { data } = await this.$axios.post('/user/verify', {
          username: this.username,
          email: '951045989@qq.com'
        })
        if (data.code === 0) {
          this.noteCount = 60
          let myCount = setInterval(() => {
            this.noteCount--
            if (this.noteCount === 0) {
              clearInterval(myCount)
            }
          }, 1000)
        }
      }
    },
    async signup() {
      try {
        const { data } = await this.$axios.post('/user/signup', {
          username: this.username,
          password: CryptoJs.MD5(this.password).toString(),
          email: '951045989@qq.com',
          code: this.note
        })
        console.log(data.msg)
        if (data.code === 0) {
          window.location.href = '/login'
        }
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.body {
  .form {
    width: 980px;
    position: relative;
    margin: 0 auto;
    padding-top: 30px;
    input {
      width: 248px;
      height: 24px;
      padding: 5px;
      border: 1px solid #aaa;
      line-height: 24px;
      margin-left: 5px;
    }
    .get-note {
      padding-left: 110px;
      margin-bottom: 10px;
      button {
        padding: 1px 8px 0;
        font-size: 12px;
        color: #333;
      }
    }
    .item {
      margin-bottom: 15px;
      .intro {
        display: inline-block;
        font-size: 14px;
        padding-top: 6px;
        width: 100px;
        text-align: right;
      }
      .warning {
        font-size: 12px;
        color: #999;
      }
    }
  }
}
</style>
