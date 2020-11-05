<template>
	<view class="navbar">
		<view class="tops" :style="{height: navheight+'px'}"></view>
		<view class="content">
			<view class="content-text">首页</view>
			<view class="content-search">
				<image class="" src="../static/index/sousuo.png" mode=""></image>
				<input type="text" value="" placeholder="搜索教学视频" />
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navheight:20
			}
		},
		created() {
			const info = uni.getSystemInfoSync();
			this.navheight = info.statusBarHeight
			// console.log(this.navheight)
		}
	}
</script>

<style >
	.content{
		width: 100%;
		height: 45px;
		background-color: #FFAA0B;
		display: flex;
		align-items: center;
		
		
	}
	.content-text{
		width: 20%;
		height: 45px;
		font-family: PingFangSC-Medium;
		display: flex;
		align-items: center;
		justify-content: center;
		color: white;
	}
	.content-search{
		width: 75%;
		height: 27px;
		background-color: white;
		border-radius: 20px;
		display: flex;
		align-items: center;
	}
	.content-search image{
		width: 18px;
		height: 18px;
		margin: 0 10px;
	}

</style>