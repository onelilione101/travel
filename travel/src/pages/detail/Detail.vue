<template>
  <detail-banner :img="detailImg"></detail-banner>
</template>

<script>
import axios from 'axios'
import DetailBanner from './components/Banner'
export default {
  name:'Detail',
  components: {
    DetailBanner
  },
  props: {
      
  },
  data () {
    return {
          detailImg: []
          
      }
    },
  computed: {
      
  },
 methods: {
    getDetailInfo () {
      axios.get('/api/detail.json')
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
       res= res.data
       if(res.ret && res.data){
         const data = res.data
         this.detailImg = data.detailImg
       }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
   
</style>