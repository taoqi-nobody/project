<template>
	<view class="content" :style="{height:winHeight+'px'}">
		<view class="statusHeight"  :style="{height:status+'px'}"></view>
		<view class="top" @click="toEdit">
			<view class="left">
				<image style="width: 56px; height: 56px; margin-right: 10px;"  src="../../static/my/m1.png" mode=""></image>
				<view class="left-1">
					<view class="">名称</view>
					<view class="">180***2264</view>
				</view>
			</view>
			<image style="width: 10px; height: 18px;" src="../../static/my/m8.png" mode=""></image>		
		</view>
		<view class="center">
			<block v-for="(item,index) in lists" :key="index" >
				<view class="list" @click="toset(index)">
					<view class="list-left">
						<image style="height: 25px; width: 25px; margin-right: 10px;" :src="item.img" mode=""></image>
						<view class="">{{item.name}}</view>
					</view>
					<image src="../../static/my/m7.png" style="width: 6px; height: 11px;" mode=""></image>
				</view>
			</block>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				winHeight:500,
				status:20,
				lists:[
					{img:'../../static/my/m2.png',name:'校区编号'},
					{img:'../../static/my/m3.png',name:'校区选择'},
					{img:'../../static/my/m4.png',name:'所属关系'},
					{img:'../../static/my/m5.png',name:'班级'},
					{img:'../../static/my/m6.png',name:'设置'},
				]
			}
		},
		mounted() {
			const info = uni.getSystemInfoSync();
			this.winHeight = info.windowHeight;
			this.status = info.navigationBarHeight;
			console.log(status)
		},
		methods: {
			toEdit(){
				uni.navigateTo({
					url:'./editData'
				})
			},
			toset(e){
				console.log(e)
				if(e==4){
					uni.navigateTo({
						url:'./set'
					})
				}else if(e==0){
					uni.navigateTo({
						url:'./schoolnum'
					})
				}else if(e==3){
					uni.navigateTo({
						url:'./class'
					})
				}else if(e==1){
					uni.navigateTo({
						url:'./selection'
					})
				}
			}
		}
	}
</script>

<style scoped>
	.content{
		width: 100%;
		background-color: #eee;
	}
	.statusHeight{
		width: 100%;
		background-color: #FFAA0B;
	}
	.top{
		width: 94%;
		height: 100px;
		background-color: #FFAA0B;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding:0 3%;
	}
	.left{
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 15px;
		color: white;
	}
	.list{
		width: 94%;
		height: 40px;
		padding: 0 3%;
		border-bottom: 1px solid #eee;
		background-color: white;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.list-left{
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 16px;
		color: #333333;
		font-family: PingFang;
	}
</style>
