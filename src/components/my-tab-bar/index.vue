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
    <div class="middle-item">
      <div class="serve"></div>
    </div>
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
  .my-tab-bar{
    position fixed
    left 0
    bottom 0
    width 750rpx
    height 100rpx
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
        margin-top -20rpx
      }
    }
  }
</style>
