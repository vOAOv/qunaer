<template>
  <div>
	 <div class="city-Show" v-for="item of showCity">{{item}}</div>
  </div>
</template>

<script>
  
  export default {
    name: 'cityShow',
    props: {
      showCity: Array
    }
  }
</script>

<style lang="stylus" scopde>
	.city-Show
	  width: 100%
	  line-height: .76rem
	  border-top: 1px solid #f5f5f5	  
	  font-size: .28rem	  	  
	  padding-left: .2rem
	  color: #21212
	  overflow: hidden
	  text-overflow: ellipsis
	  white-space: nowrap	  
</style>
