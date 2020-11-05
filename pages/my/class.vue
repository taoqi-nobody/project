<template>
	<view class="content" :style="{height:winHeight+'px'}">
		<statusNavbar></statusNavbar>
		<view class="content-list">
			<view class="classnum">班群号</view>
			<input class="content-list-class" type="text" value="" />
			<view style="font-size: 13px; padding: 10px 15px;">请填写老师提供的版群号</view>
		</view>
		<view class="content-list">
			<view class="classnum">学生姓名</view>
			<input class="content-list-class" type="text" value="" />
			<!-- <view style="font-size: 13px; padding: 10px 15px;">请填写老师提供的版群号</view> -->
		</view>
		<view class="bottom">加入班级</view>
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
			
		}
	}
</script>

<style>
	.content{
		width: 100%;
		background-color: #eee;
	}
	.content-list{
		
	}
	.classnum{
		font-size: 18px;
		color: #333333;
		padding:10px 15px;
	}
	.content-list-class{
		width: 100%;
		height: 40px;
		background-color: white;
		padding: 0 10px;
	}
	.bottom{
		width: 80%;
		height: 45px;
		background-color: #FFDC9A;
		color: white;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-left: 10%;
		border-radius: 20px;
		margin-top: 15px;
		font-size: 15px;
	}
</style>
