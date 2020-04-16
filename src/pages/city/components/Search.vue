<template>
  <div>
    <div class="search">
      <input
        class="search-input"
        type="text"
        placeholder="输入城市名或拼音"
        v-model.trim="keyword"
      >
      <div class="clear" v-if="keyword">清除</div>
    </div>
    <div class="search-content" ref="wrapper" v-show="keyword">
      <ul>
        <li
          class="item border-bottom"
          v-for="item of this.list"
          :key="item.id"
          @click="handleCityClick"
        >{{ item.city }}</li>
        <li class="item" v-if="hasNoData">没有找到对应城市</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCityClick (e) {
      this.$emit('change', e.target.innerHTML)
      this.keyword = ''
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
      }
      this.timer = setTimeout(() => {
        // 避免频繁修改属性值
        const result = []
        this.timer = null
        clearTimeout(this.timer)
        for (const i in this.cities) {
          this.cities[i].forEach((item) => {
            if (item.spell.startsWith(this.keyword) || item.name.startsWith(this.keyword)) {
              result.push({
                id: item.id,
                city: item.name
              })
            }
          })
        }
        this.list = result
        console.log(result)
      }, 100)
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
.search
  height: .72rem
  padding: 0 .2rem
  background: $bgColor
  .search-input
    box-sizing: border-box
    width 100%
    height: .62rem
    line-height: .62rem
    padding: 0 .1rem
    text-align: center
    border-radius: .06rem
    color: $darkTextColor
.search-content
  z-index 1
  overflow hidden
  position absolute
  top 1.6rem
  left 0
  right 0
  bottom 0
  background #fff
  .item
    padding-left .2rem
    line-height .76rem
    color $blackTextColor
</style>
