<template>
	<view class="content" :style="{height:winHeight+'px'}">
		<statusNavbar></statusNavbar>
		<view class="middle">
			<view class="line1">唤起智能笔蓝牙</view>
			<view class="line2">笔尖轻触纸张直到绿灯亮起</view>
			<image style="width: 160px; height: 160px; margin-top: 13%;" src="../../static/link/write.png" mode=""></image>
		</view>
		<view class="nextbtn" @click="tonear">下一步</view>
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
				winHeight:500
			}
		},
		mounted() {
			const info = uni.getSystemInfoSync();
			this.winHeight = info.windowHeight;
			// this.status = info.navigationBarHeight;
			// console.log(status)
		},
		methods: {
			tonear(){
				uni.navigateTo({
					url:'./nearby'
				})
			}
		}
	}
</script>

<style>
	.content{
		width: 100%;
		background-color: #eee;
	}
	.middle{
		width: 100%;
		height: 420px;
		background-color: white;
		display: flex;
		flex-direction: column;
		align-items: center;
		/* justify-content: center; */
	}
	.line1{
		margin-top: 15%;
		font-size: 22px;
		color: #333333;
	}
	.line2{
		font-size: 18px;
		color: #999999;
		margin-top: 5%;
	}
	.nextbtn{
		width: 80%;
		height: 45px;
		margin-left: 10%;
		background-color: #FFAA0B;
		color: white;
		font-size: 18px;
		display: flex;
		/* flex-direction: column; */
		align-items: center;
		justify-content: center;
		margin-top: 70px;
		border-radius: 8px;
	}
</style>
