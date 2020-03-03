<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li"
                   class="item border-bottom"
                   v-for="item of List"
                   :key="item.id"
                   :to="'/detail/'+ item.id" >
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
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
    margin-top .3rem
  .item
    overflow hidden
    display flex
    height 1.9rem
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
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
      .item-button
        border-radius .1rem
        background-color: pink
        padding 0 .2rem
        margin-top .2rem
        font-size .22rem
        width 1.5rem
        line-height .44rem
</style>
