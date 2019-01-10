<template>
  <div class="my-tab-bar">
    <navigator :class="['bar-item', {'active': activeIndex === barItemIndex}]"
               v-for="(barItem,barItemIndex) in barItems"
               :key="barItemIndex"
               open-type="switchTab"
               hover-class="none" :url="barItem.path">
      <div :class="['iconfont', barItem.icon]"></div>
      <div class="name">{{ barItem.name }}</div>
    </navigator>
    <!--<div class="middle-item">-->
      <!--&lt;!&ndash;<div class="serve"></div>&ndash;&gt;-->
      <!--<image src="/static/img/test1.png" class="test"></image>-->
      <!--<div class="text">定制资料</div>-->
    <!--</div>-->
  </div>
</template>
<script>
  export default {
    props: {
      activeIndex: {
        type: Number,
        default: 0
      }
    },
    data () {
      return {
        barItems: [
          {
            name: '首页',
            icon: 'icon-mobanguanli',
            path: '/pages/index/main'
          },
          {
            name: '我的',
            icon: 'icon-yuanquan',
            path: '/pages/me/main'
          }
        ]
      }
    }
  }
</script>
<style scoped lang="stylus">
  @import "~@/common/style/color.styl"
  @import "~@/common/style/size.styl"
  .my-tab-bar{
    position fixed
    left 0
    bottom 0
    width 750rpx
    height tab-bar-height
    background #fff
    display flex
    justify-content space-between
    .bar-item{
      flex 0 0 auto
      width 250rpx
      display flex
      flex-direction column
      align-items center
      .iconfont{
        font-size 45rpx
        color #aaa
      }
      .name{
        font-size 28rpx
        color #aaa
      }
      &.active{
        .iconfont{
          color main-color
        }
        .name{
          color #333
        }
      }
    }
    .middle-item{
      position absolute
      top 0
      left 250rpx
      width 250rpx
      height 100rpx
      display flex
      flex-direction column
      align-items center
      .serve{
        width 100rpx
        height 100rpx
        border-radius 50%
        border 1rpx solid main-color
        margin-top -6rpx
      }
      .test{
        flex 0 0 auto
        width 120rpx
        height 120rpx
        margin-top - 60rpx
      }
      .text{
        margin-top -20rpx
        font-size 20rpx
        color #fff
        padding 2rpx 8rpx
        border-radius 18rpx
        background #8CD5CA
        background: -webkit-linear-gradient(to right, #8CD5CA, #71C6B8);  /* Chrome 10-25, Safari 5.1-6 */
        background: linear-gradient(to right, #8CD5CA, #71C6B8); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
      }
    }
  }
</style>
