<template>
	<div>
	 	<div class="location-containner">
			<h6 class="area-title">您的位置</h6>
			<div class="location">
				<div class="location-city city-select"  ref="selectCity">{{city}}</div>
			</div>
		</div>
		<div class="hotCity-containner">
			<h6 class="area-title">热门城市</h6>
			<div class="hot-city location">
				<div class="hotCity-city location-city" v-for="item of hotCityInfo" @click="handleCityClickChange">{{item.city}}</div>
			</div>
		</div>
		<div class="DomesticCityList-container">
			<div v-for="city of domesticCityList"  :ref="city[0]">
				<h6 class="area-title">{{city[0]}}</h6>
				<div class="inland-citylist" v-for="item of city[1]">{{item.cityarea}}</div>
			</div>
		</div>
		<div class="selector">
			<h5 class="selector-item" v-for="index of domesticCityList" @click="handleCityClickRolling">{{index[0]}}</h5>
		</div>
 	</div>
</template>
<script>
  export default {
    name: 'cityList',
    props: {
      hotCityInfo: Array,
      domesticCityList: Array,
      city: String
    },
    methods: {
      handleCityClickChange (e) {
        const city = e.target.innerHTML
        this.$bus.$emit('change', city)
        this.$router.go(-1)
      },
      handleCityClickRolling (e) {
        this.target = e.target
        const name = this.target.innerHTML
        if (document.documentElement.scrollTop || document.documentElement.scrollTop === 0) {
          document.documentElement.scrollTop = this.$refs[name][0].offsetTop - 44
        } else {
          document.body.scrollTop = this.$refs[name][0].offsetTop - 44
        }
      }
    }
  }
</script>
<style lang="stylus" scoped>
	.area-title		
		font-size: .26rem
		line-height: .54rem
		padding-left: .3rem
		background: #f5f5f5
		color: #616161
	.location
		padding: .04rem .5rem .26rem .2rem
		background: #fff
		overflow: hidden			
		.location-city
			width: 30%
			line-height: .56rem
			box-sizing: border-box
			border: .02rem solid #c9cccd
			border-radius: .06rem					
			margin-top: .2rem
			color: #212121
			overflow: hidden
			text-overflow: ellipsis
			text-align: center
			white-space: nowrap			
		.city-select
			border-color: #00afc7
			color: #00afc7
	.hot-city
		display: flex
		flex-direction: row
		flex-wrap: wrap
		justify-content: space-between
	.inland-citylist
		width: 100%
		line-height: .76rem
		border-top: 1px solid #f5f5f5		
		font-size: .28rem				
		padding-left: .2rem
		color: #21212
		overflow: hidden
		text-overflow: ellipsis
		white-space: nowrap		
	.selector
		position: fixed
		right: 0
		top: 22%	
		.selector-item			
			font-size: .24rem
			line-height: .33rem
			padding-right: 0.1rem
			color: #00afc7
			text-align: center		
</style>
