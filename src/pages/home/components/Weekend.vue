<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul class="weekend-list">
      <li class="weekend-item" v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="weekend-item-img" :src="item.imgUrl">
        </div>
        <div class="weekend-item-info">
          <div class="weekend-item-title">{{ item.title }}</div>
          <div class="weekend-item-desc">{{ item.desc }}</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
@import '~@/assets/styles/mixins.styl'
.weekend-title
  height .44rem
  line-height .44rem
  padding .24rem 0 .26rem .2rem
  font-size .32rem
  color $blackTextColor
.item-img-wrapper
  overflow hidden
  width 100%
  height 0
  padding-bottom 35.67%
  .weekend-item-img
    width 100%
.weekend-item-info
  padding .14rem .2rem .2rem
  .weekend-item-title
    padding-right 1.4rem
    line-height .48rem
    font-size .28rem
    color $blackTextColor
    ellipsis()
  .weekend-item-desc
    padding-right 1.4rem
    line-height .42rem
    font-size .24rem
    color $darkTextColor
    ellipsis()
</style>
