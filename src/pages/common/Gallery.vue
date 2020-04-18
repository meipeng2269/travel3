<template>
  <div class="container" @click="handleGalleryClick">
    <div class="wrapper">
      <swiper>
        <swiper-slide v-for="(item, index) of gallaryImgs" :key="index">
          <img class="swiper-img" :src="item">
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  props: {
    gallaryImgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container >>> .swiper-container
  overflow inherit
.container
  display flex
  flex-direction column
  justify-content center
  z-index 1
  position fixed
  left 0
  right 0
  top 0
  bottom 0
  width 100%
  background #212121
  .wrapper
    /*overflow hidden*/
    width 100%
    height 0
    padding-bottom 100%
    .swiper-img
      display block
      width 100%
    .swiper-pagination
      width 100%
      height 1rem
      color #fff
</style>
