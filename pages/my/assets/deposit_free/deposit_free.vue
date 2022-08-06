<template>
	<view class="whole">
		<view class="head">
			<p>我的免押额度</p>
		</view>
		<view class="body">
			<view class="body_top">
				<view class="body_top_left">
					<p>50000.00</p>
					<text>免押金额度(元)</text>
				</view>
				<view class="body_top_right">
					<p>42924.00</p>
					<text>可用额度(元)</text>
				</view>
			</view>
			<view class="body_zhong">
				<p>已用额度</p>
				<text>￥ 7076.00</text>
			</view>
			<view class="body_bottom">
				<p>审核状态</p>
				<text>审核通过</text>
			</view>
		</view>
		<view class="leg">
			<view class="leg_left" @click="apply">
				申请提额
			</view>
			<view class="leg_zhong" @click="basicInformation">
				基本信息
			</view>
			<view class="leg_right" @click="perfect">
				完善补充信息
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				
			}
		},
		methods:{
			// 申请提额
			apply(){
				uni.navigateTo({
					url:"./apply"
				})
			},
			// 基本信息
			basicInformation(){
				uni.navigateTo({
					url:"./basic"
				})
			},
			// 完善补充信息
			perfect(){
				uni.navigateTo({
					url:"perfect"
				})
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #f9f9f9;
		overflow: hidden;
	}
	.head{
		width: 750rpx;
		height: 460rpx;
		background: linear-gradient(#ff6200, #fe9011);
		display: flex;
		justify-content: center;
	}
	.head p{
		font-size: 36rpx;
		font-weight: 900;
		color: #fff;
		margin-top: 100rpx;
	}
	.body{
		width: 690rpx;
		height: 360rpx;
		border-radius: 10px;
		background-color: #ffffff;
		position: absolute;
		top: 240rpx;
		left: 30rpx;
	}
	.body_top{
		width: 550rpx;
		height: 186rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.body_top_left{
		width: 274rpx;
		height: 92rpx;
		border-right: 1px solid #cccccc;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.body_top_left p{
		font-size: 36rpx;
		font-weight: 900;
	}
	.body_top_left text{
		font-size: 24rpx;
		color: #a1a1a1;
	}
	.body_top_right{
		width: 274rpx;
		height: 92rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.body_top_right p{
		font-size: 36rpx;
		font-weight: 900;
	}
	.body_top_right text{
		font-size: 24rpx;
		color: #a1a1a1;
	}
	.body_zhong{
		width: 550rpx;
		height: 84rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.body_zhong p{
		font-size: 24rpx;
		color: #a1a1a1;
	}
	.body_zhong text{
		font-size: 24rpx;
		margin-left: 322rpx;
	}
	.body_bottom{
		width: 550rpx;
		height: 84rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.body_bottom p{
		font-size: 24rpx;
		color: #a1a1a1;
	}
	.body_bottom text{
		font-size: 24rpx;
	}
	.leg{
		width: 690rpx;
		height: 76rpx;
		/* background-color: aqua; */
		margin: 0 auto;
		margin-top: 214rpx;
		display: flex;
		justify-content: space-between;
	}
	.leg_left{
		width: 190rpx;
		height: 70rpx;
		border-radius: 10rpx;
		border: 1px solid #ff6100;
		display: flex;
		justify-content: center;
		align-items: center;
		color: #ff6100;
		font-size: 24rpx;
	}
	.leg_zhong{
		width: 190rpx;
		height: 70rpx;
		border-radius: 10rpx;
		border: 1px solid #ff6100;
		display: flex;
		justify-content: center;
		align-items: center;
		color: #ff6100;
		font-size: 24rpx;
	}
	.leg_right{
		width: 190rpx;
		height: 70rpx;
		border-radius: 10rpx;
		border: 1px solid #ff6100;
		display: flex;
		justify-content: center;
		align-items: center;
		color: #ff6100;
		font-size: 24rpx;
	}
</style>