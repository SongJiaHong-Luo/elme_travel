<template>
<div>
  <router-link
    tag="div"
    to="/"
    class="header-abs"
    v-show="showAbs">
    <span class="iconfont">&#xe604;</span>
  </router-link>
  <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">景点详情
    <router-link to="/">
      <div class="iconfont detail-header">&#xe604;</div>
    </router-link>
  </div>
</div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position absolute
    top:.2rem
    left:.2rem
    width: .8rem
    height: .8rem
    line-height: .8rem
    border-radius .4rem
    color: #ffffff;
    background:rgba(0, 0, 0, .6);
    text-align center
    .iconfont
      color: #ffffff;
      font-size:.45rem
  .header-fixed
    z-index: 2;
    position: fixed;
    top: 0
    left: 0
    right: 0
    height $Height
    line-height $Height
    color #ffffff
    text-align center
    background-color: $bgColor;
    font-size .35rem
    .detail-header
      position absolute
      top: 0
      left: 0
      text-align center
      font-size .45rem
      color #fff
      width .64rem
</style>
