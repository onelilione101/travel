<template>
<div>
<div class="title">周末去哪儿</div>
<ul>
    <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="item-img-wrapper">
        <img :src="item.imgUrl" class="item-img">
        </div>
        <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-text">{{item.text}}</p>
        </div>
    </li>
</ul>
</div>
</template>

<script>
export default {
    name:'HomeWeekend',
    data () {
        return {
           weekendList:[{
              id: '0001',
              imgUrl: require('../../../assets/img/weekend/mountain.png'), 
              title: '邂逅绝美武功山',
              text: '徒步华东户外圣地'
            }, {
              id: '0002',
              imgUrl: require('../../../assets/img/weekend/lake.png'), 
              title: '千岛湖骑行',
              text: '给自己一次挑战，一次敬畏的旅程'
            }, {
              id: '0003',
              imgUrl: require('../../../assets/img/weekend/paraglider.png'), 
              title: '翱翔大尖山',
              text: '穿越云端，与太阳肩并肩'
            } ]
    }
 }
}
</script>

<style lang="stylus" scoped>
     @import '~styles/mixins.styl'
    .title
      line-height: .8rem
      background: #eee
      text-indent: .3rem
      font-size: .3rem
      letter-spacing: .03rem
    //   margin-top: .1rem
    .item-img-wrapper
      overflow: hidden
      height: 0
      padding-bottom: 56% 
      .item-img
        width:100%
    .item-info
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .58rem
        font-size: .32rem
        ellipsis()
       .item-text
        line-height: .44rem
        color: #ccc
        ellipsis()


</style>