<template>
 <ul class="list">
   <li class="item" v-for="(item,key) of cities" :key="key">{{key}}</li>
  </ul>
</template>

<script>
export default {
    name:'CityAlphabet',
    props: {
        cities: Object
    },
    data () {
        return {

    }
 }
}
</script>

<style lang="stylus" scoped>
     @import '~styles/varibles.styl'
     .list
       display: flex
       flex-direction: column
       justify-content: center
       position: absolute 
       top: 1.58rem
       right: 0
       bottom: 0
       width: .5rem
       padding-top: 1.3rem
       text-align: center 
       .item
         line-height: .4rem
         color: #7abad3
 
</style>


