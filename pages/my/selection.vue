<template>
	<view class="content">
		<statusNavbar></statusNavbar>
		<u-index-list :scrollTop="scrollTop">
			<view v-for="(item, index) in indexList" :key="index">
				<u-index-anchor :index="item" />
				<view class="list-cell">
					列表1
				</view>
				<view class="list-cell">
					列表2
				</view>
				<view class="list-cell">
					列表3
				</view>
			</view>
		</u-index-list>
	</view>
</template>

<script>
	import statusNavbar from '../../components/statusNavbar.vue'
	export default {
		components:{
			statusNavbar
		},
		data() {
			return {
				scrollTop: 0,
				indexList: ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U",
					"V", "W", "X", "Y", "Z"
				]
			}
		},
		onPageScroll(e) {
			this.scrollTop = e.scrollTop;
		}
	}
	
</script>

<style  scoped>
	.list-cell {
		display: flex;
		box-sizing: border-box;
		width: 100%;
		padding: 10px 24rpx;
		overflow: hidden;
		color: #323233;
		font-size: 14px;
		line-height: 24px;
		background-color: #fff;
	} 
</style>