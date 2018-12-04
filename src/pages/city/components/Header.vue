<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <span class="iconfont back-header">&#xe624;</span>
    </router-link>
  </div>
</template>

<script>
export default{
	name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl';
  .header
    position: relative
    overflow: hidden
    height: .86rem
    line-height: .86rem
    text-align: center
    color: #fff
    background: $bgColor
    font-size: .32rem
    .back-header
      position: absolute
      left: 0 
      top: 0
      width: .64rem
      float: left
      text-align: center     
      font-size: .32rem
      color: #fff
</style>
