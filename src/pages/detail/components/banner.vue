<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg" class="banner-img" />
      <div class="banner-info">
        <div class="banner-title">{{ this.sightName }}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          {{ this.bannerImgs.length }}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallery
        :imgs="bannerImgs"
        v-show="showGallery"
        @close="handleGalleryClose"
      ></common-gallery>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/gallery'
import FadeAnimation from 'common/fade/fadeAnimation'

export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data() {
    return {
      showGallery: false
    }
  },
  methods: {
    handleBannerClick() {
      this.showGallery=true
    },
    handleGalleryClose() {
      this.showGallery=false
    }
  },
  components: {
    CommonGallery,
    FadeAnimation
  }
}
</script>

<style lang='stylus' scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height 0.6rem
      background-image linear-gradient(to bottom,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title
        flex 1
        font-size 0.32rem
        padding 0.2rem
      .banner-number
        padding 0 0.4rem
        height 0.32rem
        line-height 0.32rem
        margin-top 0.14rem
        font-size 0.24rem
        border-radius 0.2rem
        background rgba(0,0,0,0.8)
        color #fff
        .banner-icon
          font-size 0.24rem
</style>
