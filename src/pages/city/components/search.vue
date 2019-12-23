<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="请输入" />
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang='stylus' scoped>
  .search
    height 0.72rem
    padding 0.1rem
    background $bgColor
    .search-input
      box-sizing border-box
      width 100%
      height 0.62rem
      padding 0 0.1rem
      line-height 0.62rem
      text-align center
      border-radius 0.6rem
      color #666
</style>
