<template>
<div>
  <detail-banner :img="detailImg"></detail-banner>
  <detail-header></detail-header>
  <div class="content">
    <detail-list></detail-list>
  </div>
</div>
</template>

<script>
import axios from 'axios'
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name:'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
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
   .content
     height: 40rem
</style>