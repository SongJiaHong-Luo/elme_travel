<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of List" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    List: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import'~styles/mixins.styl'
  .title
    line-height:.8rem
    background-color: #cccccc
    font-weight 700
    padding-left: .2rem
  .item
    padding-bottom .4rem
    .item-img-wrapper
      overflow hidden
      height 0
      padding-bottom 33.9%
      .item-img
        width 100%
    .item-info
      flex 1
      min-width 0
      padding .1rem
      .item-title
        ellipsis()
        line-height .54rem
        font-size .32rem
      .item-desc
        ellipsis()
        color #ccc
        line-height .4rem
</style>
