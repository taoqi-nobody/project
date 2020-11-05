<template>
	<view class="content">
		<statusNavbar></statusNavbar>
		<view style="width: 100%;height: 15px; background-color: #eee;" class="line"></view>
		<view class="center">
			<block v-for="(item,index) in dataList" :key="index" >
				<view class="list" @click="todetail(index)">
					<view class="title" style="">{{item.label}}</view>
					<view class="list-right">
						<image style="height: 33px; width: 33px;" v-if="index==0" :src="item.name" mode=""></image>
						<view v-if="index!=0" class="list-right-tex"  >{{item.name}}</view>
						<image v-if="index!=4"  src="../../static/my/m7.png" style="width: 6px; height: 11px; margin-left: 15px;" mode=""></image>
						<!-- <u-select v-if="index==3" v-model="show" mode="single-column" :list="list" ></u-select> -->
					</view>
					
				</view>
			</block>
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
				dataList:[
					{label:'头像',name:'../../static/my/m1.png'},
					{label:'姓名',name:'小明'},
					{label:'用户名',name:'小明'},
					{label:'性别',name:'男'},
					{label:'手机号',name:'183****5784'},
					{label:'出生日期',name:'2016-18-31'},
					{label:'家庭住址',name:'四川成都锦江区'},
				],
				show: false,
				list: [
					{
						value: '1',
						label: '男'
					},
					{
						value: '2',
						label: '女'
					}
				],
			}
		},
		methods: {
			todetail(e){
				console.log(e)
				if(e==1){
					uni.navigateTo({
						url:'changeName'
					})
				}else if(e==2){
					uni.navigateTo({
						url:'changeTitle'
					})
				}else if(e==3){
					this.show = true;
				}
			},
			
		}
	}
</script>

<style>
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
	.title{
		font-size: 15px;
		color: #333333;
		font-family: PingFang;
	}
	.list-right{
		display: flex;
		justify-content: center;
		align-items: center;
		/* font-size: 16px; */
		
	}
	.list-right-tex{
		font-size: 12px;
		color: #999999;
	}
</style>
