<template>
	<view class="content" :style="{height:winHeight+'px'}">
		<statusNavbar></statusNavbar>
		<view class="lists">
			<view class="equipment" v-for="(item,index) in list" :key="index">{{item}}</view>
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
				winHeight:500,
				list:['NILV71FD56','LGUN1470IJ']
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
	.lists{
		width: 100%;

		padding: 10px 0;
	}
	.equipment{
		width: 94%;
		height: 45px;
		padding: 0px 3%;
		background-color: white;
		/* margin-top: 20px; */
		font-size: 17px;
		display: flex;
		align-items: center;
		color: #808080;
		border-bottom: 1px solid #eee;
		
		
	}
	
</style>
