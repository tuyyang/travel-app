<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{ this.city }}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import {mapState, mapGetters} from 'vuex'

export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city']),
    // ...mapGetters(['doubleCity'])
  }
}
</script>

<style lang='stylus' scoped>
  //1rem = html font-size = 50px
  @import '~styles/varibles.styl'

  .header
    display flex
    height $headerHeight
    background $bgColor
    color #fff
    .header-left
      width 0.64rem
      float left
      .back-icon
        text-align center
        font-size 0.4rem
        margin-top 0.25rem
    .header-input
      flex 1
      height 0.64rem
      line-height 0.64rem
      margin-top 0.12rem
      margin-left 0.2rem
      background #fff
      color #ccc
      border-radius 0.1rem
    .header-right
      min-width 1.04rem
      padding 0.1rem
      float right
      text-align center
      margin-top 0.2rem
      color #fff
      .arrow-icon
        margin-left -0.06rem
        font-size 0.24rem
</style>
