<template>
 <div class="list" ref="wrapper">
   <div class="content">

     <div class="area">
         <div class="title border-topbottom">当前城市</div>
         <div class="button-list">
             <div class="button-wrapper">
               <div class="button">{{this.$store.state.city}}</div>
              </div>
              
         </div>
     </div>

     <div class="area">
         <div class="title border-topbottom">热门城市</div>
         <div class="button-list">
             <div class="button-wrapper" 
             v-for="item of hot" 
             :key="item.id"
             @click="handleCityClick(item.name)"
             >
               <div class="button">{{item.name}}</div>
              </div>
              
         </div>
     </div>

     <div 
       class="area" 
       v-for="(item, key) of cities" 
       :key="key"
       :ref="key"
    >
         <div class="title border-topbottom">{{key}}</div>
         <div class="item-list">
             <div class="item border-bottom"
             v-for="innerItem of item"
             :key="innerItem.id"
             @click="handleCityClick(innerItem.name)"
             >
               {{innerItem.name}}
             </div>
         </div>
     </div>

    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
    name:'CityList',
    mounted () {
      this.scroll = new Bscroll(this.$refs.wrapper)
    },
    methods: {
      handleCityClick (city) {
          this.$store.commit('changeCity',city)
          this.$router.push('/')
      }
    },
    watch:{
      letter () {
        if(this.letter) {
          const element = this.$refs[this.letter][0]
          this.scroll.scrollToElement(element)
        }
      }
    },
    props: {
        cities: Object,
        hot: Array,
        letter: String
    },
    data () {
        return {

    }
 }
}
</script>

<style lang="stylus" scoped>
     @import '~styles/varibles.styl'
     .border-topbottom
       &:before
         border-color: #ccc
       &:after
         border-color: #ccc
     .border-bottom
       &:before
         border-color: #ccc
     .list
       overflow: hidden
       position: absolute 
       top: 1.58rem
       left: 0
       right: 0
       bottom: 0
      .title                  //这里开始到下面有一格没缩进
        line-height: .5rem
        background: #eee
        padding-left: .2rem
        font-size: .26rem
        letter-spacing: .03rem
      .button-list
        padding: .1rem
        overflow: hidden
        padding: .1rem .6rem .1rem .1rem
        .button-wrapper
          float: left
          width: 33.33%
          .button
            margin: .1rem
            padding: .1rem 0
            text-align: center
            border: .02rem solid #ccc
            border-radius: .06rem
            letter-spacing: .03rem
      .item-list
        padding-top: .1rem
        .item
          line-height: .76rem
          padding-left: .2rem
        

</style>


