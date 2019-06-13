<template>
<div>
<div class="title">热销推荐</div>
<ul>
    <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img :src="item.imgUrl" class="item-img">
        <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-text">{{item.text}}</p>
            <button class="item-button">查看详情</button>
        </div>
    </li>
</ul>
</div>
</template>

<script>
export default {
    name:'HomeRecommend',
    data () {
        return {
            recommendList:[{
              id: '0001',
              imgUrl: require('../../../assets/img/recommend/summer.png'), 
              title: '夏季尖叫·水上达人',
              text: '丰富海鲜大餐，水上尖叫狂欢'
            }, {
              id: '0002',
              imgUrl: require('../../../assets/img/recommend/walking.png'), 
              title: '吴越古道·山野逐溪',
              text: '徒步吴越古道登浙西天池，穿越山林'
            }, {
              id: '0003',
              imgUrl: require('../../../assets/img/recommend/island.png'), 
              title: '小众海岛·中国圣托里尼之旅',
              text: '只需一个周末，拥有海天一线的视觉盛宴'
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
      margin-top: .1rem
    .item                                  //item和title怎么就平级了？？？？
      overflow: hidden
      display: flex
      height: 1.9rem
      .item-img
        width: 1.7rem
        height: 1.7rem
        padding: .1rem
      .item-info
        flex: 1
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
        .item-button
          line-height: .44rem
          margin-top: .16rem
          background: #ff9300
          padding: 0 .2rem
          border-radius: .06rem
          color: #fff

</style>