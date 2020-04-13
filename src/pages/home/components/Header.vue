<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe77f;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe680;</span>
      <span class="content">输入城市/景点/游玩主题</span>
    </div>
    <div class="header-right">
      <span>内蒙古自治区</span>
      <span class="iconfont">&#xe6aa;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
// style 里需要用@import
@import "~@/assets/styles/varibles.styl"
.header
  display flex
  flex-direction row
  height .88rem
  line-height .88rem
  color #fff
  background $bgColor
  .header-left
    width .4rem
    padding 0 .2rem
    font-size .4rem
    text-align center
  .header-input
    flex 1
    height .6rem
    line-height .6rem
    margin .14rem 0
    color #e4e7ea
    border-radius .06rem
    background #fff
    .iconfont
      padding-left .2rem
    .content
      padding-left .1rem
  .header-right
    padding 0 .22rem
</style>
