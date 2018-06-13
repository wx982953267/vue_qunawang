<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1803/7b/7b023b9728f0834fa3.img.jpg_600x330_5f4c76f7.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">世界花卉大观园(AAAA景区)</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe60f;</span>39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show='showGallary' @close="handleGallaryClose"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1803/d1/d13342f9f34abb72a3.img.jpg_r_800x800_d2da8499.jpg', 'http://img1.qunarzz.com/sight/p0/1803/d6/d62e1bd921cb2071a3.img.jpg_r_800x800_69de9d96.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        line-height: .32rem
        border-radius: .2rem
        background: rgba(0,0,0,.8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
