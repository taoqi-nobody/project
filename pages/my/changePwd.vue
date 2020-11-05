<template>
	<view class="content" :style="{height:pagesHeght+'px'}">
		<statusNavbar></statusNavbar>
		<view class="top">
			<image class="timg" @click="toreturn" src="../../static/my/bleft.png" mode=""></image>
			<view class="" style="color: #333333;font-size: 20px; font-weight: 525;">修改密码</view>
			<view class="" @click="keep" style="font-size: 15px;">保存</view>
		</view>
		<view class="pwd">
			<view class="pwd-change" v-for="item in pwdlist">
				<input class="pwd-old" type="password" value="" />
				<view class="" style="font-size: 15px;margin-left: 12px;margin-top: 5px;">{{item.name}}</view>
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
				pwdlist:[
					{name:'请输入旧密码'},
					{name:'请输入新密码'}
				]
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
					url:'./set'
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
	.pwd-old{
		width: 100%;
		height: 40px;
		background-color: white;
	}
</style>
