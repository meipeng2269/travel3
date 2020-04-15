<template>
  <div class="wrapper">
    <swiper :options="swiperOptions">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="container" v-for="item of page" :key="item.id">
          <img class="icon-img" :src="item.imgUrl">
          <div class="keywords">{{ item.desc }}</div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
import lodash from 'lodash'
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      const page = this.iconList.length / 8
      // computed中避免直接修改其他属性
      const iconList = lodash.cloneDeep(this.iconList)
      for (let i = 0; i < page; i++) {
        pages.push(iconList.splice(0, 8))
      }
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
@import '~@/assets/styles/mixins.styl'
.wrapper >>> .swiper-container
  width 100%
  height 0
  padding-bottom 51.67%
.container
  overflow hidden
  float left
  width 25%
  height 0
  padding-bottom 25%
  padding-top .1rem
  text-align center
  .icon-img
    width 1.1rem
    height 1.1rem
  .keywords
    padding 0 .1rem
    margin-top .1rem
    font-size .28rem
    color $darkTextColor
    ellipsis()
</style>
