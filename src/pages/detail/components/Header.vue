<template>
	<div>
		<router-link tag="div" to="/" class="header-abs" v-show="showAbs">
			<span class="iconfont back-icon">&#xe624;</span>
		</router-link>
		<div 
			class="header-fixed" 
			v-show="!showAbs"
			:style="styleOpacity"
		>
			城市选择
		    <router-link to="/">
		      <span class="iconfont back-icon">&#xe624;</span>
		    </router-link>
		</div>
	</div>
</template>

<script>
export default {
	name: 'detailHeader',
	data () {
		return {
			showAbs: true,
			styleOpacity: {
				opacity: 0
			}
		}
	},
	methods: {
		handelScroll () {
			const scrollTop = document.documentElement.scrollTop
			if (scrollTop > 30) {
				let opacity = scrollTop / 110
				opacity = opacity > 1 ? 1 : opacity
				this.styleOpacity = { opacity: opacity }
				this.showAbs = false
			} else {
				this.showAbs = true
			}
		}
	},
	activated () {
		window.addEventListener('scroll', this.handelScroll)
	},
	// 解绑全局事件
	deactivated () {
		window.removeEventListener('scroll', this.handelScroll)
	}	
}
</script>

<style lang="stylus" scoped>
	.header-abs
		position: absolute
		left: .1rem
		top: .2rem
		width: .72rem
		height: .72rem
		line-height: .72rem
		text-align: center		
		border-radius: 100%
		background: rgba(0, 0, 0, .5)
	.back-icon
		color: #fff
		font-size: .32rem
		font-weight: bold
	.header-fixed
		position: fixed
		left: 0
		right: 0
		top: 0
		background: rgba(0, 0, 0, .75)
		height: .88rem
		line-height: .88rem
		text-align: center
		color: #fff
		font-size: .32rem
		z-index: 2
		.back-icon
			position: absolute
			left: 0
			top: 0
			width: .84rem
			float: left
			text-align: center
</style>
