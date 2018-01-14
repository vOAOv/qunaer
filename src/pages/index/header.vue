<template>
	<div class="header">
		<div class="back iconfont">&#xe600;</div>
		<div class="search">
			<span>订单填写</span>
		</div>
		<div class="login">登录</div>
	</div>
</template>

<script>
export default {
  name: 'index-header'
}
</script>

<style lang="stylus" scoped>
  @import "../../assets/stylus/varibles.styl";
  .header
    display: flex
    height: .88rem
    line-height: .88rem
    background: $bgColor
    justify-content:space-between
    .back
      width: .8rem
      height:.88rem
      text-align: center
      color: #fff
    .search
      color: #fff
      font-size: .32rem
    .login
      font-size: .32rem
      width: 1rem
      height: .88rem
      color: #fff      
</style>