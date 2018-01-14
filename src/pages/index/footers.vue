<template>
  <div>
    <div class="footer">
      <div class="footer-left">
        <div class="footer-info-price">
          <span class="footer-price">产品价格<em class="footer-price">￥</em></span>
          <span class="footer-num">50</span>
          <span class="footer-icon iconfont">&#xe6a5;</span>
      </div>
      </div>
      <div class="footer-right">提交订单</div>
    </div>
  </div>
</template>


<script>
  export default {
    'name': 'IndexFooters'
  }
</script>

<style lang="stylus" scoped>
.footer
  position: fixed
  bottom : 0
.footer-left
  float:left
  border-top: .02rem solid #ccc
  width: 3.75rem
  height: .98rem
.footer-info-price
  margin-left: .24rem
  line-height:.98rem
 .footer-price
   font-size: .24rem
   color: #ff9700
 .footer-num
   font-size: .36rem
   font-weight: 500
   color: #ff9700
 .footer-icon
   width: .26rem
   height: .14rem
.footer-right
  float: right
  text-align: center
  line-height: .98rem
  font-size: .33rem
  color: #fff
  background: #ff9700
  width: 3.75rem
  height: .98rem
</style>