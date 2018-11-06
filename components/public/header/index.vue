<template>
  <div class="m-header">
    <div class="top">
      <div class="main be-center">
        <geo/>
        <my-nav/>
      </div>
    </div>
    <div class="search">
      <div class="be-center">
        <search/>
      </div>
    </div>
  </div>
</template>

<script>
import Geo from './geo.vue'
import MyNav from './nav.vue'
import Search from './search.vue'
export default {
  components: {
    Geo,
    MyNav,
    Search
  }
}
</script>

<style lang="scss" scoped>
.m-header {
  .be-center {
    width: 1200px;
    position: relative;
    margin: 0 auto;
  }
  @media screen and (max-width: 1210px) {
    .be-center {
      width: 980px;
    }
  }
  .top {
    background: #f8f8f8;
    .main {
      display: flex;
      justify-content: space-between;
    }
  }
  .search {
    background: #fff;
    box-shadow: 0 10px 17px 0 rgba(0, 0, 0, 0.1);
  }
}
</style>
