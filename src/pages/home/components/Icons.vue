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
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination'
      },
      iconList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '景点门票'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
          desc: '滑雪季'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
          desc: '泡温泉'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/35/2640cab202c41b02.png',
          desc: '动植园'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/d0/e09575e66f4aa402.png',
          desc: '游乐园'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/59/569d3c096e542502.png',
          desc: '必游榜单'
        },
        {
          id: '0007',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/17/4bd370f3eb1acd02.png',
          desc: '演出'
        },
        {
          id: '0008',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/7f/b1ea3c8c7fb6db02.png',
          desc: '城市观光'
        },
        {
          id: '0009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/a9/ffc620dbda9b9c02.png',
          desc: '一日游'
        }
      ]
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
