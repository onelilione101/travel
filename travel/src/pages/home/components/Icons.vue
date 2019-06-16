<template>
<div class="icons">
  <swiper :options="swiperOption">
    <swiper-slide v-for="(page, index) of pages" :key="index">
      <div
      class="everyicon"
      v-for="item of page"
      :key="item.id"
      >
        <div class="icon-img">
          <img class="icon-img-content" :src="item.imgUrl">
        </div>
        <p class="icon-text">{{item.text}}</p>
      </div>
    </swiper-slide>
  </swiper>


</div>

</template>

<script>
export default {
    name:'HomeIcons',
    props: {
      list: Array
    },
    data () {
        return {
            swiperOption: {
                pagination:'.swiper-pagination',
                autoplay: false
                // loop: false
           }
        //     iconList: [{
        //       id: '0001',
        //       imgUrl: require('../../../assets/img/icons/飞机.png'),   
        //       text: '特价机票'
        //     }, {
        //       id: '0002',
        //       imgUrl: require('../../../assets/img/icons/出境.png'), 
        //       text: '出境游'
        //     }, {
        //       id: '0003',
        //       imgUrl: require('../../../assets/img/icons/定制.png'), 
        //       text: '定制游'
        //     }, {
        //       id: '0004',
        //       imgUrl: require('../../../assets/img/icons/轮船.png'), 
        //       text: '邮轮游'
        //     }, {
        //       id: '0005',
        //       imgUrl: require('../../../assets/img/icons/车票.png'), 
        //       text: '特价车票'
        //     }, {
        //       id: '0006',
        //       imgUrl: require('../../../assets/img/icons/一日游.png'), 
        //       text: '一日游'
        //     }, {
        //       id: '0007',
        //       imgUrl: require('../../../assets/img/icons/自由行.png'), 
        //       text: '自由行'
        //     }, {
        //       id: '0008',
        //       imgUrl: require('../../../assets/img/icons/攻略.png'), 
        //       text: '攻略'
        //     }, {
        //       id: '0009',
        //       imgUrl: require('../../../assets/img/icons/出境.png'), 
        //       text: '出境游'
        //     }
        //     ]
         }
    },
    computed: {
      pages () {
        const pages = []
        this.list.forEach((item, index) => {  
           const page = Math.floor(index/8)
           if(!pages[page]) {
             pages[page] =[]
           }
           pages[page].push(item)
        })
        return pages
      }
    }

}
</script>

<style lang="stylus" scoped>
@import  '~styles/varibles.styl'
@import  '~styles/mixins.styl'

  .icons >>> .swiper-container            
    height: 0
    padding-bottom: 50%
  .everyicon                        //这部分的缩进不会很奇怪吗 everyicon明明是包在swiper-container里面的 但是这里却和它平级
    position: relative              //而且swiper（写option的） 和 它的儿子swiper-slide之间 莫名出现两个div
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    background:transparent
    text-align: center
    .icon-img
      box-sizing: border-box
      padding: .2rem
      background:transparent       
      .icon-img-content
        height:1rem
    .icon-text
      font-size: .3rem
      letter-spacing: .03rem
      color: $darkTextColor
      ellipsis()



  // .icons
  //   overflow: hidden
  //   height: 0
  //   padding-bottom: 50%
  //   background:transparent
  //   .everyicon
  //     position: relative
  //     overflow: hidden
  //     float: left
  //     width: 25%
  //     height: 0
  //     padding-bottom: 25%
  //     background:transparent
  //     text-align: center
  //     .icon-img
  //       box-sizing: border-box
  //       padding: .2rem
  //       background:transparent       
  //       .icon-img-content
  //         height:1rem
  //     .icon-text
  //       font-size: .34rem
  //       color: $darkTextColor


  // .icons
  //   overflow: hidden
  //   height: 0
  //   padding-bottom: 50%
  //   background:skyblue
  //   .everyicon
  //     position: relative
  //     overflow: hidden
  //     float: left
  //     width: 25%
  //     height: 0
  //     padding-bottom: 25%
  //     background:orange
  //     .icon-img
  //       position: absolute 
  //       top: 0
  //       left: 0
  //       right: 0
  //       bottom: .44rem
  //       box-sizing: border-box
  //       padding: .3rem
  //       background:purple         
  //     .icon-img-content
  //       display: block
  //       margin: 0 auto
  //       height:100%  
  //       // margin-top:.26rem
  //       // font-size: .34rem
  //       // color: $darkTextColor
</style>


