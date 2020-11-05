<template>
	<view class="content" :style="{height:status+'px'}">
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				status:20
			};
		},
		created() {
			const info = uni.getSystemInfoSync();
			// this.winHeight = info.windowHeight;
			this.status = info.navigationBarHeight;
			// console.log(status)
		}
	}
</script>

<style>
	.content{
		background-color: #ffffff;
		width: 100%;
	}
</style>
