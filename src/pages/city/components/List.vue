<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area border-bottom">
        <div class="title">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <button class="button">北京</button>
          </div>
        </div>
      </div>
      <div class="area border-bottom">
        <div class="title">热门城市</div>
        <ul class="button-list">
          <li class="button-wrapper" v-for="item of hotCities" :key="item.id">
            <button class="button">{{ item.name }}</button>
          </li>
        </ul>
      </div>
      <div class="area border-bottom" v-for="(value, name) in cities" :key="name" :ref="name">
        <div class="title">{{ name }}</div>
        <ul class="item-list" v-for="item of value" :key="item.id">
          <li class="item border-bottom">{{ item.name }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
.list
  position absolute
  top 1.6rem
  right 0
  bottom 0
  left  0
  overflow hidden
  .border-bottom
    &:before
      border-color #ccc
    &:after
      border-color #ccc
  .title
    height .6rem
    line-height .6rem
    color $darkTextColor
    background #eee
    padding-left .2rem
  .button-list
    overflow hidden
    /*box-sizing border-box*/
    padding .1rem .6rem .1rem 0
    .button-wrapper
      float left
      width 33.33%
      height .6rem
      line-height .6rem
      text-align center
      .button
        margin .1rem
        padding 0 .4rem
        background #fff
        font-size .2rem
        color $darkTextColor
        border 1px solid $bgColor
        border-radius .06rem
  .item-list
    .item
      padding-left .2rem
      line-height .76rem
</style>
