<template>
<div class="header">
    <div class="header-left">
        <div class="iconfont back-icon iconfanhui"></div>
    </div>
    <div class="header-input">
        <span class="iconfont iconfangdajing"></span>
        输入城市/景点/游玩主题</div>
    <div class="header-right">{{this.city}}
        <span class="iconfont arrow-icon iconjiantouarrow486"></span>
    </div>
</div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
      city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'   //在css中引入其他css 要用波浪线~
.header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #000
    .header-left
        width: .64rem
        float: left
        .back-icon
          text-align: center
          font-size: .48rem
    .header-input
        flex: 1
        height: .64rem
        line-height: .64rem
        margin-top: .12rem
        margin-left: .2rem
        padding-left: .2rem
        background: #fff
        border-radius: .1rem
        color: #ccc
    .header-right
        width:1.24rem 
        float: right
        text-align: center
        .arrow-icon
          margin-left: -.04rem
          font-size: .36rem
</style>