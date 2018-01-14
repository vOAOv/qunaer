<template>
  <div>
    <div class="message-info">
      <div class="info-row">
        <div  class="info-value">
          <span class="info-span">游客1</span>
          <input type="text" placeholder="游客姓名" class="info-input">
          <span class="info-list iconfont">&#xe615;</span>
        </div>
      </div>
      <div class="info-row">
        <div  class="info-value">
          <span class="info-span">手机号</span>
          <span class="info-86 iconfont">+86&#xe6a7;</span>
          <input type="text" placeholder="请填写手机号" class="info-input">
        </div>
      </div>
      <div class="info-row">
        <div  class="info-value">
          <span class="info-span">身份证</span>
          <input type="text" placeholder="请填写正确的省份证号码" class="info-input">
        </div>
      </div>
    </div>
    <p class="phone">咨询电话</p>
  </div>

</template>

<script>
  export default {
    name: 'index-message'
  }
</script>

<style lang="stylus" scoped>
.info-row
  overflow: hidden
  min-height: .5rem
  padding: .24rem
  border-top: .01rem solid #eee
.info-value
  line-height: .5rem
  display: flex
  align-items: center
.info-span
  width:2rem
.info-86
  font-size: .21rem
  color: #ccc
  text-align: center
  width: .78rem
  height: .5rem
  border: .01rem solid #ccc
.info-input
  float: left
  width: 100%;
  height: .38rem
  padding: .06rem 0
  border: 0
.info-list
  float: right
  display: black
  width: .4rem
  height: .4rem
  color: #00aec9
.phone
  margin-right: .24rem
  float: right
  color: #00aec9
  font-size: .2rem
</style>