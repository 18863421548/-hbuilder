<template>
	<view class="whole">
		<view class="head">
			<p>申请额度</p>
		</view>
		<view class="body">
			<view class="body_top">
				<p>免保证金额度</p>
				<text>50000.00</text>
			</view>
			<view class="body_zhong">
				<p>剩余可以额度</p>
				<text>42924.00</text>
			</view>
			<view class="body_bottom">
				<p>申请额度</p>
				<input type="text" placeholder="请输入本次申请额度">
			</view>
		</view>
		<button class="but" @click="perfect">完善补充信息</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			perfect(){
				uni.navigateTo({
					url:"./perfect"
				})
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #f5f5f5;
	}
	.head{
		width: 690rpx;
		height: 86rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.head p{
		font-size: 26rpx;
		color: #ff6100;
		margin-top: 34rpx;
	}
	.body{
		width: 690rpx;
		height: 267rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.body_top{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.body_top p{
		margin-left: 10rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.body_top text{
		margin-left: 362rpx;
		font-size: 26rpx;
	}
	.body_zhong{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.body_zhong p{
		margin-left: 10rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.body_zhong text{
		margin-left: 362rpx;
		font-size: 26rpx;
	}
	.body_bottom{
		width: 650rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.body_bottom p{
		margin-left: 10rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.body_bottom input{
		width: 234rpx;
		margin-left: 294rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 26rpx;
		font-weight: 900;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 50rpx;
	}
</style>