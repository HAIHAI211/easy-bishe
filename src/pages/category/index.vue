<template>
  <div class="me-page">
    我的页面
    <my-tab-bar :activeIndex="1"/>
  </div>
</template>
<script>
  import MyTabBar from '@/components/my-tab-bar'

  export default {
    components: {
      MyTabBar
    }
  }
</script>

<style lang="stylus" scoped>
  @import "~@/common/style/mixin.styl"
  @import "~@/common/style/color.styl"
  .me-page{
  }
</style>
