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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          title: '故宫',
          desc: '东方宫殿建筑代表，世界宫殿建筑典范'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_140x140_abb362a7.jpg',
          title: '南山滑雪场',
          desc: '北京专业级滑雪圣地'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/f4/f467729126949c3a.water.jpg_140x140_ef235b1c.jpg',
          title: '天安门广场',
          desc: '我爱北京天安门，天安门上太阳升'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/40/40b2b6c951b28fdd.water.jpg_140x140_1c863e5c.jpg',
          title: '水立方',
          desc: '中国的荣耀，阳光下的晶莹水滴'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201308/23/b283071686e64dfec8d65eac.jpg_140x140_8c5a7c49.jpg',
          title: '温都水城养生馆',
          desc: '各种亚热带植物掩映其间仿佛置身热带雨林'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'
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
    padding-left .24rem
    .recommend-info-title
      margin-top .26rem
      height .44rem
      line-height .44rem
      font-size .32rem
      color $blackTextColor
    .recommend-info-comment
      margin-top .14rem
      height .34rem
      font-size .24rem
      vertical-align text-bottom
    .recommend-info-price
      margin-top .22rem
      line-height .4rem
      font-size .24rem
</style>
