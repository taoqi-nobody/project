<template>
	<view class="content">
		<view class="top">
			<view class="" :style="{height: navheight+'px'}"></view>
			<view class="line">
				<image @click="toIndex"  src="../../static/index/fanhui.png" mode=""></image>
				<view class="" style="text-align: center; margin-left: 35%;">教学视频</view>
			</view>
		</view>
		<view class="center">
			<view class="center-1">
				<view class="center-1-tex">基础知识</view>
				<view class="center-1-btn">加入学习</view>
			</view>
			<view class="" style="width: 100%; height: 15px; background-color: #eee;"></view>
			<view class="navtop">
				<block v-for="(item,index) in title" :key="index" >
					<view class="navtop-title" :class="{active:statusIndex==index}" @click="transitem(item,index)">{{item.name}}</view>
				</block>
			</view>
			<view class="" style="width: 100%; height: 6px; background-color: #eee; margin-top: 3px;"></view>
			<view class="swiperpages">
				<swiper class="swiper" :current="activeIndex" @change="change">
					<swiper-item >
						<view class="swiper-item-1">
							<view class="swiper-item-1-title">
								课程介绍
							</view>
							<view class="swiper-item-1-stance">正确的坐姿和执笔不仅是写好字的重要前提，更能帮助书写 着保护视力，使脊柱更具持久力。
				本课程力求通过书写坐姿、执笔方法及写字工具的分类等基础知识的介绍
				做好对初学者书法的启蒙教育
				,使学习者掌握正确的书写习惯规范~~</view>
						</view>
					</swiper-item>
					<swiper-item>
						<view class="swiper-item-2">
							<block v-for="item in list">
								<view class="swiper-item-2-list">									
									<view class="">{{item.name}} </view>
								</view>
							</block>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<!-- <image class="cimg" style="" src="../../../static/index/tech1.jpg" mode=""></image> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navheight:20,
				statusIndex:0,
				activeIndex:0,
				persent:'',
				title:[
					{name:'详情'},
					{name:'目录'}
				],
				list:[
					{name:'端正坐姿 (01- 11)'},
					{name:'正确执笔 (04- 15)'},
					{name:'用笔要领 (02- 21)'},
				]
			}
		},
		created() {
			const info = uni.getSystemInfoSync();
			this.navheight = info.statusBarHeight
			// console.log(this.navheight)
		},
		methods: {
			transitem(item,index){
				this.statusIndex = index;
				this.activeIndex = index
				// console.log(this.statusIndex)
			},
			change(e){
				// console.log(e.detail.current)
				this.statusIndex = e.detail.current
			},
			toIndex(){
				uni.switchTab({
					url:'./index'
				})
			}
		}
	}
</script>

<style>
	/* .cimg{
		width: 100%; 
		height: 300px;
		position: fixed; 
		top: -30px; 
		left: 0px;
	} */
	
	.top{
		width: 100%;
		height:250px;
		background-image: url(../../static/index/tech1.jpg);
		background-repeat: no-repeat;
	}
	.top image{
		width: 10px;
		height: 18px;
		margin-left: 10px;
	}
	.line{
		width: 100%;
		height: 30px;
		display: flex;
		align-items: center;
	}
	.center{
		width: 100%;
		height: auto;
	}
	.center-1{
		width: 94%;
		height: 50px;
		display: flex;
		align-items: center;
		margin-left: 3%;
		background-color: white;
		justify-content: space-between;
	}
	.center-1-tex{
		font-weight: bold;
		font-size: 20px;
		color: #333333;
	}
	.center-1-btn{
		font-size: 13px;
		width: 79px;
		height: 25px;
		background-color: #FFAA0B;
		border-radius: 13px;
		display: flex;
		justify-content: center;
		align-items: center;
		color: white;
		font-family: PingFang;
	}
	.navtop{
		width: 100%;
		height: 40px;
		display: flex;
		align-items: center;
	}
	.navtop-title{
		width: 50%;
		font-size: 18px;
		height: 40px;
		
		color: #666666;
		display: flex;
		justify-content: center;
		align-items: center;
		border-bottom: 3px solid white;
	}
	.active{
		font-weight: bold;
		color: #333333;
		border-bottom: 3px solid #FFAA0B;
	}
	.swiperpages{
		width: 100%;
		height: auto;
	}
	.swiper{
		white-space: nowrap;
		width: 100%;
		/* height: auto; */
		height: 500px;
	}
	.line1{
		width: 100%;
		height: auto;
	}
	.swiper-item-1,.swiper-item-2{
		width: 94%;
		height: auto;
		margin-left: 3%;
	}
	.swiper-item-1-title{
		font-size: 18pt;
		color: #333333;
		margin-top: 10px;
		/* font-weight: bold; */
		
	}
	.swiper-item-1-stance{
		/* margin-top: 10px; */
		width: 80%;
		font-size: 14px;
		height: 1110px;
		color: #666666;
		margin-bottom: 20px;
		/* box-sizing: border-box;
		flex-shrink: inherit;
		word-break:break-all; */
		white-space: normal;
		/* overflow: hidden; */
		/* text-overflow: ellipsis; */
	}
	.swiper-item-2-list{
		width: 100%;
		height: 50px;
		border-bottom: 1px solid #eee;
		font-size: 15pt;
		display: flex;
		align-items: center;
		color: #666666;
		font-family: PingFang;
		white-space: normal;
	}
</style>
