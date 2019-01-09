<template>
  <div class="index-page">
    <div class="head">
      <div class="head-item">
        <image class="icon" src="/static/img/check-type.png"></image>
        <div class="name">切换题型</div>
      </div>
      <div class="head-item">
        <image class="icon" src="/static/img/kefu.png"></image>
        <div class="name">咨询客服</div>
      </div>
    </div>
    <my-tab-bar :activeIndex="0"/>
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
  .index-page{
    .head{
      display flex
      align-items center
      justify-content space-between
      background #fff
      padding 20rpx 30rpx
      .head-item{
        display flex
        align-items center
        .icon{
          width 50rpx
          height 50rpx
          margin-right 8rpx
        }
        .name{
          color #636363
          font-size 30rpx
        }
      }
    }
  }
</style>
