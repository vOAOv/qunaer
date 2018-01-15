<template>
 	<div class="header-container">
			<header class="header">
        <router-link to="/">
  				<div class="header-left iconfont">
            &#xe624;
          </div>
        </router-link>
				<div class="header-title">
					<div class="area-switch-left">国内</div>
					<div class="area-switch-right">海外</div>
				</div>
			</header>
	</div>
</template>

<script scoped>
export default {
  name: 'cityHeader'
}
</script>

<style lang="stylus" scoped>
	.header-container
		width: 100%
		height: .88rem
		position: fixed
		left: 0
		top: 0
		background: #00bcd4
		.header
			height: .88rem
			display: flex
			align-items: center
			background: #00bcd4			
			flex-direction: row
			justify-content: center
			overflow: hidden
			text-align: center
			.header-left
				width: .58rem
				line-height: .88rem
				font-size: .4rem
				padding: .1rem
				font-weight: bold
				position: absolute
				left: 0				
				top: 0
				color: #fff
			.header-title				
				height: .56rem
				width: 4rem
				border-radius: .1rem
				display: flex
				flex-direction: row
				background: #fff
				.area-switch-left					
					line-height: .54rem
					width: 2rem
					border: 1px solid #fff					
					border-radius: .1rem
					color: #00bcd4
					background: #fff
				.area-switch-right
					line-height: .54rem
					width: 2rem
					border: 1px solid #fff
					border-radius: .1rem
					background: #00bcd4
					color: #fff				
</style>
