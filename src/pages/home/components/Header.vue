<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
       输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div> 
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl';
  .header 
    display: flex
    height: .86rem
    line-height: .86rem
    color: #fff
    background: $bgColor
    .header-left
      width: .64rem
      float: left
      text-align: center
      .back-icon        
        font-size: .4rem
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      padding-left: .2rem
      margin-top: .12rem
      margin-left: .2rem
      color: #ccc
      background: #fff
      border-radius: .1rem
    .header-right
      min-width: 1.04rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff
      .arrow-icon
        margin-left: -.04rem
        font-size: .24rem
</style>
