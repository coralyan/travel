<template>
  <div class="wrap-com">
    <div class="com-title">周末去哪儿</div>
    <ul>
      <li v-for="item of recommentList" :key="item.id" class="com-item border-bottom">
        <div class="item-img-wrap">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <h3 class="item-title">{{item.title}}</h3>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
	name: 'HomeWeekend',
  data () {
    return {
      recommentList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }, {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }, {
        id: '03',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }, {
        id: '04',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins.styl'
  .com-title
    margin-top: .2rem
    padding-left: .2rem
    line-height: .8rem
    color: #212121
  .com-item
    overflow: hidden
    .item-img-wrap
      overflow: hidden
      heihgt: 0
      padding-bottom: 36.65%
    .item-img
      position: absolute
      width: 100%
    .item-info
      padding: .12rem .2rem .3rem;
      .item-title
        line-height: .54rem
        font-size: .32rem
        color: #212121;
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #626262
        ellipsis()
</style>
