<template>
<div>
  <div class="banner" @click="handleBannerClick">
    <img class="banner-img" src="https://imgs.qunarzz.com/sight/p0/1505/d2/d274c92de14c93da.water.jpg_r_800x800_9b38d300.jpg">
    <div class="banner-info">
      <div class="img-count">
        <span class="iconfont">&#xe7b3;</span>
        <span class="number">53</span>
      </div>
      <div class="banner-title">颐和园(AAAAA景区)</div>
    </div>
  </div>
  <common-gallery
    :imgs="imgs"
    v-if="showGallery"
    @close="handleGalleryClose"
  ></common-gallery>
</div>
</template>

<script>
import CommonGallery from '../../common/Gallery'
export default {
  name: 'DeatilBanner',
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false,
      imgs: [{
        id: 1,
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1505/d2/d274c92de14c93da.water.jpg_r_800x800_9b38d300.jpg'
      }, {
        id: 2,
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1910/21/2155967acb775f3ba3.img.jpg_r_800x800_3164041f.jpg'
      }, {
        id: 3,
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1905/25/25f5e945d9a1f6f7a3.img.jpg_r_800x800_a315d1ee.jpg'
      }]
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position relative
  overflow hidden
  height 0
  padding-bottom 55%
  &:after
    position absolute
    left 0
    bottom 0
    content: ''
    display block
    width 100%
    height .6rem
    background-image linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
  .banner-img
    width 100%
  .banner-info
    position absolute
    left .2rem
    right .2rem
    bottom .36rem
    .img-count
      width 1.2rem
      height .4rem
      line-height .4rem
      text-align center
      background rgba(0, 0, 0, .5)
      border-radius .2rem
      font-size .24rem
      color #fff
      .number
        padding-left .1rem
    .banner-title
      margin-top .2rem
      font-size .36rem
      color #fff
</style>
