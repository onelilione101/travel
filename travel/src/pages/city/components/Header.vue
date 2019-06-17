<template>
    <div class="header">城市选择
       <router-link to="/">
         <div class="iconfont header-back iconfanhui"></div>
       </router-link>
        
    </div> 
</template>

<script>
export default {
    name:'CityHeader',
    props: {
        
    },
    data () {
        return {

    }
 }
}
</script>

<style lang="stylus" scoped>
     @import '~styles/varibles.styl'
     .header
       position: relative
       overflow:hidden
       height: .86rem
       line-height: .86rem
       text-align: center
       background: $bgColor
       font-size: .36rem
       letter-spacing: .03rem
       .header-back
         position: absolute 
         top: 0
         left: 0
         width: .84rem
         text-align: center
         font-size: .48rem
         
</style>


