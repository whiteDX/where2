<template>
  <div class="header">
    <router-link to="/">
    <div class="iconfont header-back">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>
<script>
  export default {
    name:'CityHeader',
  }
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position:relative
    overflow:hidden
    height:$headerHeight
    line-height:$headerHeight
    text-align:center
    background:$bgColor
    font-size:.4rem
    color:#fff
    .header-back
      width:.64rem
      text-align:center
      font-size:.4rem
      position:absolute
      top:0
      left:0
      color:#fff
</style>
