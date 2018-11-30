<template>
  <div class="wrap-com">
    <div class="com-title">热销推荐</div>
    <ul>
      <li v-for="item of recommentList" :key="item.id" class="com-item border-bottom">
        <div class="item-img-wrap">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <h3 class="item-title">{{item.title}}</h3>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
	name: 'HomeRecomment',
  data () {
    return {
      recommentList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_200x200_b412a8a2.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }, {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_200x200_b412a8a2.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }, {
        id: '03',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_200x200_b412a8a2.jpg',
        title: '南国冰雪乐园',
        desc: '这里可以让你在南国感受到北国风光'
      }, {
        id: '04',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_200x200_b412a8a2.jpg',
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
    display: flex
    height: 1.9rem
    margin-left: .14rem
    .item-img-wrap
      margin-right: .2rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        color: #212121;
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #626262
        ellipsis()
      .item-button
        line-height: .44rem
        background: #ff9300
        padding: 0 .1rem
        margin-top: .16rem
        border-radius: .06rem
        color: #fff 
</style>
