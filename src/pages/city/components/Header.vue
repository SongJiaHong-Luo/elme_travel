<template>
  <div>
    <div class="header">城市选择
      <router-link to="/">
      <div class="iconfont city-header">&#xe604;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative;
    overflow hidden
    height $Height
    line-height $Height
    color #ffffff
    text-align center
    background-color: $bgColor;
    font-size .35rem
    .city-header
      position absolute
      top: 0
      left: 0
      text-align center
      font-size .45rem
      color #fff
      width .64rem
</style>
