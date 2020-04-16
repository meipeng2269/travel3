<template>
  <ul class="list">
    <li class="item" v-for="(value, name) of cities" :key="name">{{ name }}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
.list
  display flex
  flex-direction column
  justify-content center
  position absolute
  top 1.6rem
  right 0
  width .4rem
  .item
    line-height .4rem
    text-align center
    color $bgColor
</style>
