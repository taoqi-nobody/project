<template>
	<view class="content" :style="{height:pagesHeght+'px'}">
		<statusNavbar></statusNavbar>
		<view class="top">
			<image class="timg" @click="toreturn" src="../../static/my/bleft.png" mode=""></image>
			<view class="" style="color: #333333;font-size: 20px; font-weight: 525;">修改名称</view>
			<view class="" @click="keep" style="font-size: 15px;">保存</view>
		</view>
		<view class="pwd">
			<view class="pwd-change">
				<view class="title">用户名</view>
				<input class="pwd-old" placeholder="小明" type="password" value="" />
				<!-- <view class="pwd-old-value" style="">用户你好，为维护班级秩序，请填写真实姓名，仅次于班级内展示。请谨慎填写</view> -->
			</view>
		</view>
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
				pagesHeght:500,
				// pwdlist:[
				// 	{name:'请输入旧密码'},
				// 	{name:'请输入新密码'}
				// ]
			}
		},
		mounted() {
			const info = uni.getSystemInfoSync()
			this.pagesHeght = info.windowHeight
		},
		methods: {
			toreturn(){
				uni.navigateBack({
					delta:1
				})
			},
			keep(){
				uni.redirectTo({
					url:'./editData'
				})
			}
		}
	}
</script>

<style>
	.content{
		background-color: #eee;
		width: 100%;
	}
	.top{
		width: 94%;
		height: 44px;
		padding: 0 3%;
		background-color: white;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.timg{
		width: 20pt;
		height: 20pt;
	}
	.pwd{
		width: 100%;
		margin-top: 10px;
	}
	.pwd-change{
		margin-top: 13px;
	}
	.title{
		font-size: 18px;
		margin-left: 12px;
		margin-bottom: 5px;
	}
	.pwd-old{
		width: 94%;
		height: 40px;
		background-color: white;
		padding: 0 3%;
	}
	.pwd-old-value{
		font-size: 13px;
		margin-top: 5px; 
		color: #666666;
		width: 94%;
		height: 40px;
		padding: 0 3%;
	}
</style>
