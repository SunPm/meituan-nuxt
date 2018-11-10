<template>
  <div/>
</template>

<script>
export default {
  middleware: async ctx => {
    const { data } = await ctx.$axios.get('/user/exit')
    if (data.code === 0) {
      location.href = '/'
    }
  }
}
</script>
