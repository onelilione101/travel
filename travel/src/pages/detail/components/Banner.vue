<template>
<div>

<div class="banner">
  <swiper :options="swiperOption" v-if="showSwiper">
    <swiper-slide v-for="item of img" :key="item.id">
        <img class="banner-img" :src="item.imgUrl">
         <!-- <div class="banner-img-number">{{(index+1)}}/{{img.length}}</div> -->
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
<!-- <common-gallery></common-gallery> -->
</div>
</template>

<script>
// import CommonGallery from 'common/gallery/Gallery'
export default {
  name:'DetailBanner',
  // components: {
  //   CommonGallery
  // },
  props: {
      img: Array
  },
  data () {
    return {
      swiperOption: {
            pagination:'.swiper-pagination',
            paginationType: 'fraction',
            loop: true,
            autoplay: false
        }
      }
    },
  computed: {
        showSwiper () {
          return this.img.length
    }

},
  methods: {
    
  }
}
</script>

<style lang="stylus" scoped>
  .banner >>> .swiper-pagination-fraction
    z-index:1
    position: absolute
    left: 85%
    right: .2rem
    bottom: .3rem
    background: rgba(0,0,0,0.5)
    width: .78rem
    height: .44rem
    line-height: .44rem
    text-align: center
    font-size: .22rem
    border-radius: .21rem
  .banner
    overflow: hidden
    height: 0
    padding-bottom: 56%
    background: #eee
    position: relative
    .banner-img
      width: 100%
    .swiper-pagination
      color: #fff
    .banner-img-number
      z-index:1
      position: absolute
      right: .2rem
      bottom: .3rem
      background: rgba(0,0,0,0.5)
      color: #fff
      width: .76rem
      height: .44rem
      line-height: .44rem
      text-align: center
      font-size: .22rem
      border-radius: .21rem

   
</style>