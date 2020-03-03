<template>
    <div class="header">
      <div class="header-left">
        <div class="iconfont">&#xe604;</div>
      </div>
      <div class="header-input">
        <span class="iconfont">&#xe619;</span>
        输入城市/景点/游玩主题</div>
      <router-link to="/city">
        <div class="header-right">{{ this.city }}
          <span class="iconfont">&#xe64a;</span>
        </div>
      </router-link>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import'~styles/varibles.styl'
  .header{
    display:flex;
    line-height: $Height;
    background-color: $bgColor;
    color: #fff;
  }
  .header-left{
    width : .64rem;
    float: left;
  }
  .header-left .iconfont{
    text-align: center;
    font-size: .5rem;
  }
  .header-input{
    flex: 1;
    height:.62rem;
    line-height: .62rem;
    background-color: #fff;
    margin-top: .12rem;
    margin-left: .2rem;
    border-radius :.1rem;
    padding-left :.2rem;
    color:#ccc;
  }
  .header-right{
    min-width : 1.04rem;
    padding-left: 0 .1rem;
    float: right;
    margin-left: .1rem;
    text-align: center;
    color #fff
  }
  .header-right .iconfont{
    margin-left: -.04rem;
    font-size: .25rem;
  }
</style>
