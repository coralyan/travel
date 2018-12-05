<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" src="//img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_600x330_c0fdc96b.jpg" />
			<div class="banner-info">
				<div class="banner-num"><span class="iconfont banner-icon">&#xe692;</span>39</div>
				<div class="banner-txt">长隆野生动物世界(AAAAA景区)</div>			
			</div>
		</div>
		<common-gallary 
			:imgs="imgs" 
			v-show="showGallary"
			@close="handleGallaryClose"
		></common-gallary>
	</div>
</template>

<script>
import commonGallary from 'common/gallary/Gallary'
export default {
	name: 'detailBanner',
	components: {
		commonGallary
	},
	data () {
		return {
			showGallary: false,
			imgs: ['http://img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_350x240_28b1f356.jpg', 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_350x240_f8a69516.jpg', 'http://img1.qunarzz.com/sight/p0/1811/d4/d4a663613604238ea3.img.jpg_350x240_28b1f356.jpg']
		}
	},
	methods: {
		handleBannerClick () {
			this.showGallary = true
		},
		handleGallaryClose () {
			this.showGallary = false
		}
	}
}
</script>

<style lang="stylus" scoped>
	.banner
		overflow: hidden
		position: relative
		height: 0
		padding-bottom: 55%
		.banner-img
			width: 100%
		.banner-info
			position: absolute
			left: 0
			right: 0
			bottom: 0
			color: #fff
			.banner-num
				display: inline-block
				height: .4rem
				line-height: .4rem
				padding: 0 .3rem
				margin: 0 .2rem	
				font-size: .24rem
				text-align: center
				border-radius: .2rem
				background: rgba(0, 0, 0, .5)
			.banner-icon
				margin-right: .1rem
				font-size: .24rem
			.banner-txt
				line-height: .6rem
				padding: 0 .2rem .2rem
				font-size: .36rem	
				background-image: -webkit-linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))		
</style>
