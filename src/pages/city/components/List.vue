<template>
  <div class="city-list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title">当前城市</div>
        <ul class="item-list item-list-cur">
          <li class="item">{{this.currentCity}}</li>
        </ul>
      </div>
      <div class="area">
        <div class="title">热门城市</div>
        <ul class="item-list item-list-hot">
          <li 
            class="item" 
            v-for="item of hotCities" 
            :key="item.id"
            @click="handleCityClick(item.name)"
          >
            {{item.name}}
          </li>
        </ul>
      </div>
      <div class="area" 
        v-for="(item, key) of cities" 
        :key="key"
        :ref="key"
      >
        <div class="title">{{key}}</div>
        <ul class="item-list">
          <li 
            class="item" 
            v-for="innerItem of item" 
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"
          >
            {{innerItem.name}}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default{
	name: 'CityList',
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }      
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl';
  @import '~@/assets/styles/mixins.styl';
  .city-list
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden
  .title
    padding: .24rem .3rem
    color: #212121
    font-size: .24rem
    background: #f5f5f5
  .item-list
    position: relative
    display: flex
    flex-direction: row
    flex-wrap: wrap
    z-index: 0
    overflow: hidden
    &:before
      position: absolute
      left: 25%
      top: 0
      content: ''
      width: 25%
      height: 100%      
      border-left: .01rem solid #ddd
      border-right: .01rem solid #ddd
    &:after
      position: absolute
      right: 25%
      top: 0
      content: ''
      width: 25%
      height: 100%   
      border-right: .01rem solid #ddd
    &.item-list-hot
      &:before
        width: 33.33%
        left: 33.33%
      &:after
        content: none
      .item
        width: 33.33%
    &.item-list-cur
      &:before
      &:after
        content: none
    .item
      width: 25%
      height: .9rem
      line-height: .9rem
      font-size: .28rem
      color: #212121
      text-align: center
      border-bottom: .01rem solid #ddd
      margin-bottom: -1px
      position: relative
      z-index: 10
      ellipsis()
</style>
