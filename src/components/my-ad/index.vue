<template>
  <div class="ad" :style="{backgroundColor: bgColor}">
    <image class="ad-img" :src="src" :style="{width: imgWidth,height:imgHeight}"></image>
    <div class="name">{{name}}</div>
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
            return '/static/img/app.png'
          case 'app':
            return ''
          case 'web':
            return '/static/img/web.png'
        }
      },
      name () {
        switch (this.type) {
          case 'mp':
            return ''
          case 'app':
            return ''
          case 'web':
            return ''
        }
      },
      bgColor () {
        switch (this.type) {
          case 'mp':
            return '#F4CE6C'
          case 'app':
            return ''
          case 'web':
            return '#364153'
        }
      },
      imgWidth () {
        switch (this.type) {
          case 'mp':
            return '78rpx'
          case 'app':
            return ''
          case 'web':
            return '176rpx'
        }
      },
      imgHeight () {
        switch (this.type) {
          case 'mp':
            return '146rpx'
          case 'app':
            return ''
          case 'web':
            return '154rpx'
        }
      }
    }
  }
</script>
<style lang="stylus" scoped>
  .ad{
    width 750rpx
    height 400rpx
    display flex
    flex-direction column
    justify-content center
    align-items center
    .ad-img{
      width 78rpx
      height 146rpx
    }
  }
</style>
