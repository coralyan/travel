<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconsList"></home-icons>
    <home-recomment :list="recommentList"></home-recomment>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecomment from './components/Recomment'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default{
	name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecomment,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconsList: [],
      recommentList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('./api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconsList = data.iconsList
        this.recommentList = data.recommentList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>
</style>
