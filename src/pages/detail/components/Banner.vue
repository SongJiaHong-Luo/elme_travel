<template>
  <div>
    <div class="banner" @click="showGallaryClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">
          {{this.sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe65a;</span>
          {{this.bannerImgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary
        :imgs="bannerImgs"
        v-show="showGallary"
        @close="closeGallary"
        ></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    showGallaryClick () {
      this.showGallary = true
    },
    closeGallary () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position: relative;
  overflow: hidden;
  height: 0;
  width: 100%
  padding-bottom:55%;
  .banner-img
    width:100%;
  .banner-info
    display flex
    position absolute
    bottom: 0
    left: 0
    right: 0
    color: #fff;
    line-height: .6rem;
    background-image linear-gradient(top,rgba(0, 0, 0, 0),rgba(0, 0, 0, .8))
    .banner-title
      flex 1
      padding:0 .2rem;
      font-size: .32rem
    .banner-number
      padding 0 .4rem
      margin-top: .14rem;
      height .32rem
      line-height: .32rem;
      border-radius: .2rem;
      font-size: .24rem
      background rgba(0, 0, 0, .8)
    .banner-icon
      font-size:.24rem;
</style>
