<template>
    <div class="list" ref="wrapper">
      <div class="content">
        <div class="area">
          <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <div class="button-wrapper">
              <div class="button">{{ this.city }}</div>
            </div>
          </div>
        </div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrapper"
                 v-for="item of hot"
                 :key="item.id"
                  @click="handleCityClick(item.name)">
              <div class="button">{{ item.name }}</div>
            </div>
          </div>
        </div>
        <div class="area"
             v-for="(item, key) of cities"
             :key="key"
             :ref="key">
          <div class="title border-topbottom">{{ key }}</div>
          <div class="item-list">
            <div class="item border-bottom"
                 v-for="innerItem of item"
                 :key="innerItem.id"
                 @click="handleCityClick(innerItem.name)"
                  >
                {{ innerItem.name }}</div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default{
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState(['city'])
  },
  mounted () {
    this.$nextTick(() => {
      this.scroll = new BScroll(this.$refs.wrapper, {})
    })
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
.border-topbottom
  &:before
    border-color #ccc
  &:after
    border-color #ccc
.border-bottom
  &:before
    border-color #ccc
.list
  overflow hidden
  position: absolute;
  top 1.58rem
  bottom: 0
  left: 0
  right: 0
  .title
    font-size: .3rem;
    line-height: .54rem;
    background-color: #eeeeee;
    padding-left:.2rem
    color: #666;
  .button-list
    overflow hidden
    padding:.1rem .6rem .1rem .1rem
    .button-wrapper
      width:33.33%;
      float: left;
      .button
        text-align center
        border .02rem solid #ccc
        margin: .1rem;
        padding: .1rem 0;
        border-radius .06rem
  .item-list
    .item
      line-height: .64rem;
      padding-left .2rem
      color: #666;
</style>
