<template>
  <div class="search">
    <city-header></city-header>
    <city-search></city-search>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
export default {
    name:'City',
    props: {
        
    },
    components: {
        CityHeader,
        CitySearch
    },
    data () {
        return {

    }
 }
}
</script>

<style lang="stylus" scoped>
     @import '~styles/mixins.styl'


</style>


