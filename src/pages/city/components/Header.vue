<template>
  <div class="city-header-wrapper">
    <router-link to="/">
      <div class="city-header-left">
        <span class="iconfont">&#xe77f;</span>
      </div>
    </router-link>
    <div class="city-header-title">城市选择</div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
@import "~@/assets/styles/mixins.styl"
.city-header-wrapper
  position relative
  height .88rem
  color #fff
  background $bgColor
  .city-header-left
    position: absolute
    left 0
    top 0
    width .8rem
    height .88rem
    line-height .88rem
    text-align center
    font-size .32rem
    color #fff
  .city-header-title
    margin 0 1rem
    height .88rem
    line-height .88rem
    padding 0 .4rem
    font-size .32rem
    text-align center
    ellipsis()
</style>
