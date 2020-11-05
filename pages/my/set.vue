<template>
	<view class="content" :style="{height:pagesHeght+'px'}">
		<view class="" style="width: 100%; height: 10px;"></view>
		<view class="center">
			<view class="list" v-for="(item,index) in lists" @click="toChange(index)" :key="index">
				<view class="">{{item.name}}</view>
				<image v-if="index!=1"  :src="item.img" style="width: 6px; height: 11px;"></image>
				<view v-if="index==1" class="" style="font-size: 11px;color: #666666;">{{item.img}}</view>
			</view>
		</view>
		<view class="bottom">退出登陆</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				pagesHeght:500,
				lists:[
					{name:'修改密码',img:'../../static/my/m7.png'},
					{name:'版本',img:'v1.0.0'},
					{name:'MAC地址',img:'../../static/my/m7.png'},
				]
			}
		},
		mounted() {
			const info = uni.getSystemInfoSync()
			this.pagesHeght = info.windowHeight
		},
		
		methods: {
			toChange(e){
				if(e==0){
					uni.navigateTo({
						url:'./changePwd'
					})
				}
			}
		}
	}
</script>

<style scoped>
	.content{
		background-color: #eee;
		width: 100%;
	}
	.center{
		width: 94%;
		padding: 0 3%;
		background-color: white;
	}
	.list{
		width: 100%;
		height: 40px;
		color: #666666;
		background-color: white;
		display: flex;
		font-size: 15px;
		align-items: center;
		justify-content: space-between;
		border-bottom: 1px solid #eee;
	}
	.bottom{
		width: 80%;
		height: 45px;
		background-color: white;
		color: red;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-left: 10%;
		border-radius: 20px;
		margin-top: 15px;
		font-size: 15px;
	}
		
</style>
