<template>
<div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
    <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <!-- <swiper-slide><img class="swiper-img" src="~img/desert.png"></swiper-slide>    //!!!!!直接在标签里写src可以用我设的缩写 ~img，放到data里就行不通，会报错
    <swiper-slide><img class="swiper-img" src="~img/mountain.png"></swiper-slide>
    <swiper-slide><img class="swiper-img" src="~img/galaxy.png"></swiper-slide> -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
    name:'HomeSwiper',
    props: {
        list: Array
    },
    data () {
        return {
            swiperOption: {
                pagination:'.swiper-pagination',
                loop: true,
                autoplay: false
                // autoplay: {
                //     delay:3000,
                //     disableOnInteraction: false
                // },

                // speed:2800
            }
         }
        },
            computed: {
                showSwiper () {
                  return this.list.length
                }
            }
            // swiperList: [{
            //     id: '0001',
            //     imgUrl:require('../../../assets/img/desert.png')      //!!!!!   本地图片加个require，然后把img地址包起来就可以了
            // },{
            //     id: '0002',
            //     imgUrl:require('../../../assets/img/mountain.png')   
            // },{
            //     id: '0003',
            //     imgUrl:require('../../../assets/img/galaxy.png')    
            // }]
        }
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: rgba(255,255,255,0.7)
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.2%     //根据使用图片的高/宽*100 形成百分比  这里我直接用的是375*117 所以比例是31.2% 如果原图尺寸不是375*117 那么按原图的
    background: #eee    // eee比ccc更淡
    .swiper-img
      width: 100%
    
</style>