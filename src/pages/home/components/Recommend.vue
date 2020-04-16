<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <div class="recommend-container border-bottom" v-for="item of recommendList" :key="item.id">
      <div class="recommend-img-wrapper">
        <img class="recommend-img" :src="item.imgUrl">
      </div>
      <div class="recommend-info">
        <div class="recommend-info-title">{{ item.title }}</div>
        <div class="recommend-info-comment">31720条评论</div>
        <div class="recommend-info-price">¥140</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
@import '~@/assets/styles/mixins.styl'
.recommend-title
  height .44rem
  line-height .44rem
  padding .24rem 0 .26rem .2rem
  font-size .32rem
  color $blackTextColor
.recommend-container
  display flex
  margin-left .24rem
  padding .24rem 0
  .recommend-img-wrapper
    width 2rem
    height 2rem
    .recommend-img
      width 100%
  .recommend-info
    flex 1
    min-width 0
    padding-left .24rem
    .recommend-info-title
      margin-top .26rem
      height .44rem
      line-height .44rem
      font-size .32rem
      color $blackTextColor
      ellipsis()
    .recommend-info-comment
      margin-top .14rem
      height .34rem
      font-size .24rem
      vertical-align text-bottom
      ellipsis()
    .recommend-info-price
      margin-top .22rem
      line-height .4rem
      font-size .24rem
      ellipsis()
</style>
