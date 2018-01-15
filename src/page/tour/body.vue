<template style="z-index: -999;position: relative;">
  <div>
    <div class="list" v-for="item of list" :key="item.id">
      <div class="pic">
        <img :src="item.Url"/>
      </div>
      <div class="info">
        <div class="avtive">{{item.alt}}}</div>
        <div class="adress">
          <h3>{{item.address}}出发</h3>
          <p>{{item.info}}</p>
        </div>
        <h1 class="price">￥{{item.price}}<span>起</span></h1>
        <h2 class="sell">{{item.sell}}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'tour-Body',
  props: {
		list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .list
    height 2rem
    padding .2rem
    display flex
    box-sizing border-box
    .avtive
      font-size .3rem
    .pic
      img
        width 1.6rem
        height 1.6rem
    .info
      padding-left .2rem
      height 1.6rem
      flex 1
      display flex
      flex-direction column
      justify-content space-between
      position relative
      &:after
        content " "
        height .02rem
        width 100%
        background #c9cccd
        position absolute
        bottom -.2rem
      .adress
        display flex
        h3
          color #00bcd4
        p
          font-size .24rem
          color #616161
      .price
        text-align right
        font-size .28rem
        color #ff8300
        span
          font-size .24rem
          color #9e9e9e
          padding-left .02rem
      .sell
        font-size .24rem
        color #9e9e9e
</style>
