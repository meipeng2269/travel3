<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    test
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper
  },
  data () {
    return {
      content: 'home'
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
