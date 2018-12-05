<template>
	<div>
		<detail-banner></detail-banner>
		<detail-header></detail-header>		
		<div class="content">
			<detail-list :list="list"></detail-list>
		</div>
	</div>
</template>

<script>
import detailBanner from './components/Banner'
import detailHeader from './components/Header'
import detailList from './components/List'
export default {
	name: 'Detail',
	components: {
		detailBanner,
		detailHeader,
		detailList
	},
	data () {
		return {
			list: [{
				title: '成人票',
				children: [{
					title: '成人联票一',
					children: [{
						title: '成人联票一(去哪儿网售票)'
					}]
				}, {
					title: '成人联票二'
				}, {
					title: '成人联票三'
				}]
			}, {
				title: '儿童票'
			}, {
				title: '学生票'
			}]
		}
	}
}
</script>

<style lang="stylus" scoped>
	.content
		height: 50rem
</style>
