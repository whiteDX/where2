<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题</div>
    <router-link to="/city">
      <div class="header-right">{{city}}
        <span class="iconfont arrow-icon">&#xe614;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default{
  name: 'HomeHeader',
  props:{
    city:String
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display:flex
    height:$headerHeight
    background:$bgColor
    color:#ffffff
    .header-left
      height:$headerHeight
      line-height:$headerHeight
      width:.64rem
      float:left
    .header-input
      flex:1
      line-height:.62rem
      height:.62rem
      margin-top:.12rem
      margin-left:.2rem
      background:#fff
      border-radius:.1rem
      color: #ccc
    .header-right
      height:$headerHeight
      line-height:$headerHeight
      width:1.24rem
      float:right
      text-align:center
      color:white
      .arrow-icon
        margin-left:.04rem
        font-size:.24rem
</style>
