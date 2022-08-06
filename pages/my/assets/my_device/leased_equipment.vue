<template>
	<view class="whole">
		<view class="head">
			<view class="head_top">
				<view :class="activite==1?'unexpired':'click_unexpired'" @click="ckeckIndex(1)">
					<p>未到期在租设备（64）</p>
				</view>
				<view :class="activite==2?'expired':'click_expired'" @click="ckeckIndex(2)">
					<p>已到期未归还设备（39）</p>
				</view>
			</view>
			<view class="head_bottom">
				<input type="text" placeholder="请输入设备序列号/订单号">
				<image src="../../../../static/fdj2.jpg" mode=""></image>
				<p>查询</p>
			</view>
		</view>
		
		
		
		
		
		
		<view class="all_order_second" v-show="activite==1">
			<view class="heads">
				<p>订单号</p>
				<text>2011061410254891002</text>
				<span>9/36</span>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>¥ 113.00/月</p>
						<text>免保证金3100.00元</text>
					</view>
				</view>
			</view>
			<view class="leg">
				<p>序列号 5CG0166DQY</p>
				<view class="see" @click="order_details">查看订单</view>
			</view>
		</view>
		
		
		
		
		
		
	</view>
</template>

<script>
	export default{
		data(){
			return{
				activite: 1,
			}
		},
		methods:{
			ckeckIndex(e) {
				this.activite = e
			},
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #f5f5f5;
		overflow: hidden;
	}
	.head{
		width: 750rpx;
		height: 198rpx;
		background-color: #fcfcfc;
	}
	.head_top{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
	}
	.unexpired{
		width: 345rpx;
		height: 88rpx;
		display: flex;
		align-items: center;
		font-size: 26rpx;
		color: #ff6100;
		
	}
	.unexpired p{
		margin-left: 30rpx;
	}
	.click_unexpired{
		width: 345rpx;
		height: 88rpx;
		display: flex;
		align-items: center;
		font-size: 26rpx;
		color: #000;
	}
	.click_unexpired p{
		margin-left: 30rpx;
	}
	.expired{
		width: 345rpx;
		height: 88rpx;
		display: flex;
		align-items: center;
		font-size: 26rpx;
		color: #ff6100;
	}
	.expired p{
		margin-left: 44rpx;
	}
	.click_expired{
		width: 345rpx;
		height: 88rpx;
		display: flex;
		align-items: center;
		font-size: 26rpx;
		color: #000;
	}
	.click_expired p{
		margin-left: 44rpx;
	}
	.head_bottom{
		width: 690rpx;
		height: 110rpx;
		margin: 0 auto;
		display: flex;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.head_bottom input{
		width: 556rpx;
		height: 70rpx;
		border-radius: 40rpx;
		background-color: #f5f5f5;
		font-size: 24rpx;
		padding-left: 64rpx;
	}
	.head_bottom image{
		width: 28rpx;
		height: 28rpx;
		position: absolute;
		left: 50rpx;
	}
	.head_bottom p{
		font-size: 26rpx;
	}
	
	
	
	
	.all_order_second{
		width: 690rpx;
		height: 443rpx;
		border-radius: 10px;
		background-color: #fff;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.heads{
		width: 690rpx;
		height: 66rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
		font-size: 26rpx;
	}
	.heads p{
		margin-left: 20rpx;
	}
	.heads text{
		margin-left: 9rpx;
	}
	.heads span{
		margin-left: 190rpx;
		color: #ff6100;
	}
	.body{
		width: 690rpx;
		height: 257rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
	}
	.body_left{
		width: 187rpx;
		height: 257rpx;
	}
	.body_left image{
		width: 138rpx;
		height: 79rpx;
		margin-top: 50rpx;
		margin-left: 30rpx;
	}
	.body_right{
		width: 504rpx;
		height: 257rpx;
		/* background-color: aqua; */
		display: flex;
		flex-direction: column;
	}
	.body_right_name{
		width: 442rpx;
		height: 99rpx;
		margin-top: 30rpx;
	}
	.body_right_name p{
		background-color: #e81717;
		color: #fff;
		width: 110rpx;
		height: 34rpx;
		border-radius: 40rpx;
		font-size: 22rpx;
		position: absolute;
		text-align: center;
	}
	.body_right_name text{
		display: block;
		text-indent: 118rpx;
		font-size: 24rpx;
		font-weight: 900;
	}
	
	.body_right_time{
		width: 474rpx;
		height: 76rpx;
		display: flex;
		justify-content: space-between;
	}
	.body_right_time p{
		font-size: 22rpx;
		color: #999999;
		margin-top: 31rpx;
	}
	.body_right_time text{
		font-size: 26rpx;
		font-weight: 900;
		margin-top: 26rpx;
	}
	.body_right_price{
		width: 450rpx;
		height: 52rpx;
		/* background-color: blueviolet; */
		display: flex;
	}
	.body_right_price p{
		font-size: 26rpx;
		font-weight: 900;
	}
	.body_right_price text{
		font-size: 20rpx;
		margin-left: 24rpx;
		margin-top: 3rpx;
	}
	.leg{
		width: 690rpx;
		height: 120rpx;
		display: flex;
		align-items: center;
	}
	.leg p{
		font-size: 26rpx;
		margin-left: 20rpx;
	}
	.see{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 26rpx;
		margin-left: 234rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
</style>