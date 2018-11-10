<template>
  <div class="page-register">
    <my-header/>
    <my-body/>
  </div>
</template>

<script>
import MyHeader from '../components/register/header'
import MyBody from '../components/register/body'
export default {
  components: {
    MyHeader,
    MyBody
  },
  layout: 'blank'
}
</script>

<style lang="scss" scoped>
</style>
