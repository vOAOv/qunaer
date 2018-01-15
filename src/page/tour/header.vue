<template>
  <div class="header" style="z-index: 999;position: relative;">
      <div class="header-top">
          <a href="javascript:;"> < </a>
          <div class="search">
              <input type="text" placeholder="输入城市或景点" value="一日游" />
          </div>
          <span>搜索</span>
      </div>
      <div class="header-bottom">
      	<div class="header-bottom-info">
          <div class="header-bottom-left">
              <p>全部分类</p>
          </div>
          <div class="header-bottom-middle" @click="handleChooseClick">
              <p>全部目的地</p>
          </div>
          <div class="header-bottom-right">
              <p>推荐排序</p>
          </div>
         </div>
         <div class="popout">
         	<div class="popout-address" v-if="address" @click="handleClick">
         		<p>北京</p>
         		<p>保定</p>
         		<p>唐山</p>
         		<p>张家口</p>
         		<p>承德</p>
         	</div>
         </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'tour-Header',
  data () {
		return {
  		address: false
  	}
  },
  methods: {
  	handleChooseClick () {
  		if (this.address === false) {
  			this.address = true
  		} else {
  			this.address = false
  		}
  	},
  	handleClick (e) {
  		this.$emit('change', e.target.innerHTML )
  	}
  }
}
</script>

<style lang="stylus" scoped>
    .header-top
        height .88rem
        background #00bcd4
        display flex
        justify-content space-between
        align-items center
        padding 0 .2rem
        a
            display block
            padding-right .2rem
        .search
            flex 1
            margin-left .2rem
            box-sizing border-box
            padding-left .2rem
            background #fff
            border-radius .06rem
            input
                width 100%
                height .6rem
                border none
                border-radius .06rem
        span
            padding-left .2rem
            color #fff
    .header-bottom
        border 1px solid #f1f1f1
        height .8rem
        .header-bottom-info
        	display flex
        	background #f1f1f1
	        .header-bottom-left
	            flex 1
	            display flex
	            justify-content center
	            align-items center
	            background #fff
	            height .8rem
	        .header-bottom-middle
	            flex 1
	            display flex
	            justify-content center
	            align-items center
	            background #fff
	            height .8rem
	        .header-bottom-right
	            flex 1
	            display flex
	            justify-content center
	            align-items center
	            background #fff
	            height .8rem
	      .popout
	      	.popout-address
	      		background #f1f1f1
	      		p
	      			height .5rem
	      			text-align center
	      			font-size .32rem
	      			line-height .5rem   
</style>
