<template>
  <form>
    <div class="form-group">
      <div class="form-row">
        <div class="form-left">游玩日期</div>
        <div class="form-right">
          <li class="form-con">
            <p class="form-p">今天</p>
            <p class="form-p">1月13日</p>
          </li>
          <li class="form-con">
            <p class="form-p">明天</p>
            <p class="form-p">1月14日</p>
          </li>
          <li class="form-con">
            <p class="form-p">后天</p>
            <p class="form-p">1月15日</p>
          </li>
        </div>
      </div>
      <div class="form-bottom">
        <div class="form-number">购买数量</div>
        <div class="form-big">最多买五张</div>
        <div class="form-botton">
          <span class="btn-left btn">-</span>
          <span class="num-center btn">1</span>
          <span class="btn-right btn">+</span>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
  export default {
    name: 'index-formorder'
  }
</script>

<style lang="stylus" scoped>
.form-group
  margin-bottom: .2rem
.form-row
  overflow: hidden
  padding: .24rem
.form-left
  text-align: center
  line-height: 1.28rem
  color: #6c6c6c
  float: left
  width: 1.6rem
  height: 1.28rem
.form-right
  display: flex
  float: right
  width: 5.4rem
  height: 1.28rem
  align-items: center
  justify-content: space-between
.form-con
  text-align: center
  border: .01rem solid #ccc
  border-radius: .2rem
  width: 1.53rem
  height: .83rem 
.form-p
  margin-top:.1rem
  color: #6c6c6c
.form-bottom
  overflow: hidden
  padding: .24rem
  border-top: .02rem solid #f5f5f5
  border-bottom: .2rem solid #f5f5f5
.form-number
  text-align: center
  line-height: 1.28rem
  color: #6c6c6c
  float: left
  width: 1.6rem
  height: 1.28rem
.form-big
  text-align: center
  line-height: 1.28rem
  color: #c1c1c1
  float: left
  width: 1.6rem
  height: 1.28rem
  width: 1.6rem
  height: 1.28rem
.form-botton
  display: flex
  align-items: center
  float: right
  text-align: center
  line-height: 1.28rem
  height: 1.28rem
  width: 2.2rem
.btn-left
  display: block
  border: .01rem solid #ccc
  border-right: 0
  color: #cdd4da
  font-weight: 900
  background: #efefef
  width: .6rem
  height: .6rem
.num-center
  border: .01rem solid #ccc
  border-left: 0
  border-right: 0
  width: .7rem
  height: .6rem
.btn-right
  display: block
  background: #00aec9
  color: #fff
  font-weight: 900
  width: .6rem
  height: .6rem
  border: .01rem solid #ccc
  border-left: 0
.btn
  text-align: center
  line-height: .6rem
</style>