<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrappar">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="(item, key) in imgs" :key="key">
            <img  class="gallary-img" :src="item" alt="">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return ['http://img1.qunarzz.com/sight/p0/1803/d1/d13342f9f34abb72a3.img.jpg_r_800x800_d2da8499.jpg', 'http://img1.qunarzz.com/sight/p0/1803/d6/d62e1bd921cb2071a3.img.jpg_r_800x800_69de9d96.jpg']
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>
<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: initial
  .container
    display: flex
    flex-direction: column
    justify-content: center
    z-index: 99
    position: fixed
    left: 0
    right: 0
    top: 0
    bottom: 0
    background: #000
    .wrappar
      overflow: hidden
      width: 100%
      padding-bottom: 100%
      .gallary-img
        width: 100%
      .swiper-pagination
        color: #fff
        bottom: -1rem

</style>
