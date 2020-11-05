<template>
	<view class="content">
		<navbar></navbar>
		<view class="top"></view>			
		<view class="top-1">
			<!-- <image class="timg" src="../../../static/index/top-img.png" mode=""></image> -->
			<view class="box">开始练字</view>
		</view>
		<view class="center">
			<view class="list">
				<image class="simg" src="../../static/index/center1.png" mode=""></image>
				<view class="tex" >视频回放</view>
			</view>
			<view class="list" >
				<image class="simg" src="../../static/index/center2.png" mode=""></image>
				<view class="tex" @click="toteching">教学视频</view>
			</view>
			<view class="list">
				<image class="simg" src="../../static/index/center3.png" mode=""></image>
				<view class="tex">练习记录</view>
			</view>
			
		</view>
		<view class="center" style="margin-top: 20px;">
			<view class="list">
				<image class="simg" src="../../static/index/center4.png" mode=""></image>
				<view class="tex">教学评分</view>
			</view>
			<view class="list">
				<image class="simg" src="../../static/index/center5.png" mode=""></image>
				<view class="tex">系统评分</view>
			</view>
			<view class="list">
				<image class="simg" src="../../static/index/center6.png" mode=""></image>
				<view class="tex">练习详情</view>
			</view>
			
		</view>
		<view class="rank">
			<view class="rank-text" style="">当得分排名</view>
			<view class="right">
				<view class="rigth-text">更多</view>
				<image style="width: 8px; height: 8px;" src="../../static/index/right.png" mode=""></image>
			</view>
		</view>
		<view class="bottom">
			<view class="b-1">
				<image class="bimg" src="../../static/index/bottom1.jpg" mode=""></image>
				<view class="bottom-text1">嘿嘿</view>
				<view class="bottom-text2">02</view>
			</view>
			<view class="b-2">
				<image style="width: 32px; height: 27px;" src="../../static/index/guanjun.png" mode=""></image>
				<image class="bimg" src="../../static/index/bottom2.jpg" mode=""></image>
				<view class="bottom-text1">阿明</view>
				<view class="bottom-text2">01</view>
			</view>
			<view class="b-1" style="">
				<image class="bimg" src="../../static/index/bottom3.jpg" mode=""></image>
				<view class="bottom-text1">小雷</view>
				<view class="bottom-text2">03</view>
			</view>
		</view>
			
	</view>
</template>

<script>
	import navbar from '../../components/navbar.vue'
	export default {
		components:{
			navbar
		},
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {
			toteching(){
				uni.navigateTo({
					url:'./teaching'
				})
			}
		}
	}
</script>

<style>
	.top{
		width: 100%;
		height: 100px;
		background-color: #FFAA0B;
		position: relative;
	}
	.top-1{
		width: 94%;
		height: 150px;
		position:absolute;
		top: 55px;
		left: 3%;
		border-radius: 10px;
		/* z-index: 1; */
		background-image: url(../../static/index/top-img.png);
		margin: auto;
		background-repeat: no-repeat;
	}
	/* .timg{
		width: 94%;
		height: 150px;
		margin: 5px auto;
		margin-left: 3%;
		
		
		
		
	} */
	.box{
		width: 150px;
		height: 50px;
		box-shadow:0 0 9px 3px rgba(49,32,0,0.1);
		color: #FFAA0B;
		font-size: 22px;
		font-family: PingFangSC-Medium;
		border-radius: 25px;
		margin: auto;
		display: flex;
		justify-content: center;
		align-items: content;
		line-height: 50px;
		margin-top: 126px;
		/* position: fixed; */
		/* z-index: 2; */
		background-color: white;
		/* bottom: 0px; */
		/* top: 30px; */
	/* 	top: 120px; */
		/* z-index: 20;
		top: -20px; */
		/* margin-top: 20px; */
		
	}
	.center{
		width: 94%;
		height: 50px;
		margin-top: 100px;
		display: flex;
		margin-left: 3%;
		justify-content: space-between;
	}
	.list{
		/* width: 108px; */
		width: 30%;
		height: 44px;
		border: 1px solid #eee;
		border-radius: 10px;
		display: flex;
		align-items: center;
		/* justify-content: center; */
		/* margin: 0 5px; */
	}
	.simg{
		width: 44px;
		height: 44px;
		margin-right: 5px;
	}
	.tex{
		
		font-size: 13px;
	}
	.rank{
		width: 94%;
		height: 50px;
		display: flex;
		margin-left: 3%;
		justify-content: space-between;
		margin-top: 20px;
	}
	.rank-text{
		font-family: PingFangSC-Medium; 
		font-weight: 550;
		color: #333333;
		font-size: 18px;
	}
	.right{
		width: 40px;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.rigth-text{
		font-size: 11px;
	}
	.bottom{
		width: 80%;
		height: 160px;
		/* border: 1px solid #eee; */
		margin-left: 10%;
		display: flex;
		justify-content: space-between;
	}
	.b-1{		
		border-radius: 5px;
		/* margin-top: 20px; */
		/* margin-left: 15%; */
		background-color: white;
		height: 150px;
		width: 35%;
		box-shadow:0 0 9px 3px rgba(49,32,0,0.1);
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		position: relative;
		top: 20px;
		z-index: 1;
	}
	.b-2{
		height: 150px;
		width: 30%;
		margin-left: 95px;
		border-radius: 5px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		box-shadow:0 0 9px 3px rgba(49,32,0,0.1);
		background-color: white;
		position: absolute;
		z-index: 2;
	}
	.bimg{
		width: 53px;
		height: 53px;
		border-radius: 26px;
	}
	.bottom-text1{
		font-size: 14px;
	}
	.bottom-text2{
		font-size: 14px;
		color: #FFAA0B;
		font-weight: bold;
	}
</style>
