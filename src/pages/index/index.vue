<template>
  <div class="index-page">
    <div class="head">
      <picker @change="_typeChange" :value="initTypeIndex" :range="types" range-key="label">
        <div class="head-item">
          <image class="icon" src="/static/img/check-type.png"></image>
          <div class="name">切换毕设类型</div>
        </div>
      </picker>
      <div class="head-item">
        <image class="icon" src="/static/img/kefu.png"></image>
        <div class="name">咨询客服</div>
      </div>
    </div>
    <div class="class-bar">
      <div class="class-bar-item">
        <div class="icon">
          <image class="img" src="/static/img/class-free.png"></image>
        </div>
        <div class="name">免费课</div>
      </div>
      <div class="class-bar-item">
        <div class="icon">
          <image class="img" src="/static/img/class-common.png"></image>
        </div>
        <div class="name">系统班</div>
      </div>
      <div class="class-bar-item">
        <div class="icon">
          <image class="img" src="/static/img/class-vip.png"></image>
        </div>
        <div class="name">精品班</div>
      </div>
    </div>
    <div class="class class-free">
      <div class="class-head">
        <div class="title">免费课</div>
        <div class="more">更多 ></div>
      </div>
      <scroll-view scroll-x class="scroll-view-h my-scroll-view">
        <div class="free-class-item">
        </div>
        <div class="free-class-item">
        </div>
        <div class="free-class-item">
        </div>
      </scroll-view>
    </div>
    <div class="class class-common">
      <div class="class-head">
        <div class="title">系统班</div>
      </div>
      <div class="class-item"></div>
    </div>
    <div class="class class-vip">
      <div class="class-head">
        <div class="title">精品班</div>
      </div>
      <div class="class-item"></div>
    </div>
    <my-tab-bar :activeIndex="0"/>
  </div>
</template>
<script>
  import MyTabBar from '@/components/my-tab-bar'
  import MyPicker from '@/components/my-picker'
  export default {
    components: {
      MyTabBar,
      MyPicker
    },
    data () {
      return {
        types: [
          {
            value: 'mp',
            label: '小程序'
          },
          {
            value: 'app',
            label: 'APP(安卓,苹果)'
          },
          {
            value: 'web',
            label: 'WEB(H5,网站)'
          }
        ],
        initTypeIndex: 0
      }
    },
    methods: {
      _typeChange (e) {
        console.log(e.mp.detail.value)
        wx.setNavigationBarTitle({
          title: this.types[e.mp.detail.value].label + '毕设'
        })
      }
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
      border-bottom 1rpx solid line-color
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
    .class-bar{
      background #fff
      border-bottom 1rpx solid line-color
      padding 30rpx 0
      display flex
      .class-bar-item{
        flex 1 0 0
        display flex
        flex-direction column
        align-items center
        .icon{
          width 110rpx
          height 110rpx
          background #F6F6F6
          border-radius 50%
          margin-bottom 26rpx
          center()
          .img{
            width 50rpx
            height 50rpx
          }
        }
        .name{
          font-size 28rpx
          color #333
        }
      }
    }
    .class{
      background #fff
      border-top 1rpx solid line-color
      border-bottom 1rpx solid line-color
      margin-top 30rpx
      padding-bottom 30rpx
      .class-head{
        padding 25rpx 0rpx
        display flex
        align-items center
        justify-content center
        position relative
        .title{
          font-size 30rpx
          color #333333
        }
        .more{
          position absolute
          right 10rpx
          font-size 25rpx
          color #B3B3B3
        }
      }
      &.class-free{
        .my-scroll-view{
          padding-right 20rpx
          .free-class-item{
            display inline-block
            width 560rpx
            height 300rpx
            background main-color
            border-radius 12rpx
            margin-left 20rpx
          }
        }
      }
      &.class-common{
        .class-item{
          margin 0 auto
          width 700rpx
          height 390rpx
          border-radius 12rpx
          background main-color
        }
      }
      &.class-vip{
        .class-item{
          margin 0 auto
          width 700rpx
          height 390rpx
          border-radius 12rpx
          background main-color
        }
      }
    }
  }
</style>
