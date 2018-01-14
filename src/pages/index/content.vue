<template>
	<div class="con-info">
    <div class="con-info-left">
    	<h2 class="con-title">【上午场】故宫成人票+故宫全景手绘地图</h2>
    	<ul class="con-taglist">
    		<li class="con-tagitem">2018-01-14</li>
    		<li class="con-tagitem">不可退</li>
    	</ul>
    </div>
    <div class="con-info-right">
    	<div class="con-info-price">
    		<span class="con-price">￥<em class="info-price">50</em></span>
    		<span>起</span>
    		/张
    	</div>
    	<div class="con-nont">预定须知</div>
    </div>
    <div class="con-bottom"></div>
	</div>
</template>

<script>
  export default {
    name: 'index-content'
  }
</script>

<style lang="stylus" scoped>
    .con-info
      // min-height: 1.66rem
    .con-info-left
      color: #212121
      font-size: .32rem
      line-height: .44rem
      width: 5.18rem
      height:1.69rem
      float: left
    .con-title
      margin: .1rem .1rem
    .con-tagitem
      float: left
      color: #616161
      font-size: .24rem
      line-height: .44rem
      margin:.2rem .2rem
    .con-info-right
      overflow: hidden
      text-align: center
      width: 2.32remx
      height: 1.69rem
    .con-info-price
      float: right
      line-height:.44rem
      color: #9e9e9e
      margin:.2rem .2rem
      font-size: .24rem
      height: .44rem
    .con-price
      color: #ff8300
    .info-price
      font-size: .35rem 
    .con-nont
      float: right
      margin: 0 .2rem
      color: #00bcd4
    .con-bottom
      height: .2rem
      width: 7.5rem
      background: #f5f5f5
       
</style>