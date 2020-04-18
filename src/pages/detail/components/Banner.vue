<template>
<div>
  <div class="banner" @click="handleBannerClick">
    <img class="banner-img" :src="bannerImg">
    <div class="banner-info">
      <div class="img-count">
        <span class="iconfont">&#xe7b3;</span>
        <span class="number">53</span>
      </div>
      <div class="banner-title">{{ sightName }}</div>
    </div>
  </div>
  <common-gallery
    :imgs="imgs"
    v-if="showGallery"
    @close="handleGalleryClose"
    :gallaryImgs="gallaryImgs"
  ></common-gallery>
</div>
</template>

<script>
import CommonGallery from '../../common/Gallery'
export default {
  name: 'DeatilBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false
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
