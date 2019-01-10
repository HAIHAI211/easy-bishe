<template>
  <div class="index-page">
    <div class="head">
      <!--<div class="head-item" @click="_checkType">-->
        <!--<image class="icon" src="/static/img/check-type.png"></image>-->
        <!--<div class="name">切换毕设类型</div>-->
      <!--</div>-->
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
