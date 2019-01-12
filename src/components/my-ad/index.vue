<template>
  <div class="ad">
    <image class="ad-img" :src="src"></image>
    <div class="ad-title">{{ title }}</div>
    <div class="ad-sub-title">{{ subTitle }}</div>
  </div>
</template>
<script>
  export default {
    props: {
      type: {
        type: String,
        default: 'mp'
      }
    },
    computed: {
      src () {
        switch (this.type) {
          case 'mp':
            return '/static/img/dev-mp.png'
          case 'app':
            return '/static/img/dev-app.png'
          case 'web':
            return '/static/img/dev-web.png'
        }
      },
      title () {
        switch (this.type) {
          case 'mp':
            return '一个好汉三个帮'
          case 'app':
            return '好汉不提当年勇'
          case 'web':
            return '人在江湖身不由己'
        }
      },
      subTitle () {
        switch (this.type) {
          case 'mp':
            return '帮你个屁哦'
          case 'app':
            return '畜生驴一样'
          case 'web':
            return '渣渣你是个呆头鹅'
        }
      }
    }
  }
</script>
<style lang="stylus" scoped>
  .ad{
    width 750rpx
    height 400rpx
    position relative
    display flex
    flex-direction column
    justify-content center
    align-items center
    .ad-img{
      position absolute
      z-index -1
      top 0
      left 0
      width 100%
      height 100%
    }
    .ad-title{
      color: #444;
      font-weight: bold;
      font-size: 45rpx;
      margin-bottom 20rpx
    }
    .ad-sub-title{
      font-size 32rpx
      color #444444
    }
  }
</style>
