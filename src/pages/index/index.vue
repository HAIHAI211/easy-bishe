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
    <run-loading :state="loadingState"/>
  </div>
</template>
<script>
import {mapActions} from 'vuex'
import {getMonthMasters} from '@/http/api'
import PullToRefreshMixin from '../../utils/harrison-mp-utils/mixin/pullToRefreshMixin'
import RunLoading from '@/components/run-loading'
export default {
  mixins: [PullToRefreshMixin],
  components: {
    RunLoading
  },
  data () {
    return {
      apis: [getMonthMasters]
    }
  },
  computed: {
    formatDates () {
      let result = this.activePage.list.map(e => e.financialDate.slice(0, -3))
      return result
    }
  },
  methods: {
    ...mapActions(['FETCH_FINANCIAL_CATEGORY_LIST', 'FETCH_FINANCIAL_USER_LIST']),
    _monthCardClick (masterId) {
      wx.navigateTo({
        url: `/pages/financial-add/main?type=edit&masterId=${masterId}`
      })
    }
  },
  async mounted () {
    this.FETCH_FINANCIAL_CATEGORY_LIST()
    this.FETCH_FINANCIAL_USER_LIST()
  },
  onShow () {
    this.fetchList()
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
