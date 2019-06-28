<template>
<div>
  <router-link 
    tag="div"
    to="/" 
    class="header-back"
    v-show="showBack"
  >
    <div class="iconfont back-icon iconfanhui"></div>
  </router-link>
  <router-link tag="div" to="/" class="header-fixed" v-show="!showBack"
      :style="opacityStyle"
  >
     <div class="iconfont back-icon iconfanhui header-fixed-icon"></div>
     活动详情
  </router-link>
</div>
</template>

<script>
export default {
  name:'DetailHeader',
  props: {
      
  },
  data () {
    return {
          showBack: true,
          opacityStyle: {
            opacity: 0
          }
          
      }
    },
  computed: {
      
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60){
        let opacity = top /140
        opacity = opacity > 1 ? 1 : opacity
        this.showBack = false
        this.opacityStyle = { opacity }
        
      }else{
        this.showBack = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  },


}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
   .header-back
     z-index: 2
     position: absolute
     left: .2rem
     top: .2rem
     width: .8rem
     height: .8rem
     line-height: .8rem
     text-align: center
     border-radius: .4rem
     background: rgba(0,0,0,.8)
     .iconfanhui
       color: #fff
       font-size: .4rem
    .header-fixed
      z-index: 3
      position: fixed
      top: 0
      left: 0
      right: 0
      height: .86rem
      line-height: .86rem
      text-align: center
      background: $bgColor
      color: #000
      font-size: .32rem
      .header-fixed-icon
        position: absolute 
        top: 0
        left: 0
        width: .64rem
        font-size: .4rem
</style>