<template>
  <div>
    <router-link to="/" tag="div" class="back-icon" v-show="isShow">
      <span class="iconfont">&#xe77f;</span>
    </router-link>
    <div class="header" v-show="!isShow" :style="opacityStyle">
      <router-link to="/" tag="div" class="header-left">
        <span class="iconfont">&#xe77f;</span>
      </router-link>
      <div class="header-title">颐和园</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      isShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const scrollTop = document.documentElement.scrollTop
      if (scrollTop > 10) {
        let opacity = scrollTop / 82
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.isShow = false
      } else {
        this.isShow = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
@import "~@/assets/styles/mixins.styl"
.back-icon
  position absolute
  left .1rem
  top .1rem
  width .72rem
  height .72rem
  border-radius .36rem
  line-height .72rem
  text-align center
  color #fff
  background rgba(0, 0, 0, .5)
.header
  position fixed
  top 0
  left 0
  width 100%
  height .88rem
  color #fff
  background $bgColor
  .header-left
    position: absolute
    left 0
    top 0
    width .8rem
    height .88rem
    line-height .88rem
    text-align center
    font-size .32rem
  .header-title
    margin 0 1rem
    height .88rem
    line-height .88rem
    padding 0 .4rem
    font-size .32rem
    text-align center
    ellipsis()
</style>
