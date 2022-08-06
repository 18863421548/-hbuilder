<template>
	<view class="whole">
		<view class="order">
			<view class="order_no">
				<p>订单编号</p>
				<input type="text" placeholder="请输入订单编号">
			</view>
			<view class="original_time">
				<p>原还机时间</p>
				<text>2022年6月23日</text>
			</view>
			<view class="new_time">
				<p>原还机时间</p>
				<input type="text" placeholder="请输入新还机时间">
			</view>
		</view>
		<view class="payment">
			<view class="need_pay">
				<p>还需支付</p>
				<text>￥0.00</text>
			</view>
			<view class="wechat">
				<image src="../../../../static/wx1.jpg" mode="" class="wx"></image>
				<view class="wechat_payment">
					<p>微信支付</p>
					<text>微信内仅支持微信付款</text>
				</view>
				<image src="../../../../static/dg.jpg" mode="" class="hook"></image>
			</view>
		</view>
		<button class="but">提 交 订 单</button>
	</view>
</template>

<script>
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #f5f5f5;
		overflow: hidden;
	}
	.order{
		width: 690rpx;
		height: 260rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.order_no{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
		
	}
	.order_no p{
		margin-left: 10rpx;
		font-size: 26rpx;
	}
	.order_no input{
		width: 184rpx;
		font-size: 26rpx;
		color: #999999;
		margin-left: 344rpx;
	}
	.original_time{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.original_time p{
		margin-left: 10rpx;
		font-size: 26rpx;
	}
	.original_time text{
		font-size: 26rpx;
		margin-left: 318rpx;
	}
	.new_time{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.new_time p{
		margin-left: 10rpx;
		font-size: 26rpx;
	}
	.new_time input{
		width: 211rpx;
		font-size: 26rpx;
		color: #999999;
		margin-left: 296rpx;
	}
	.payment{
		width: 690rpx;
		height: 201rpx;
		border-radius: 10px;
		background-color: #fff;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.need_pay{
		width: 650rpx;
		height: 81rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		border-bottom: 1px solid #cccccc;
	}
	.need_pay p{
		margin-left: 10rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.need_pay text{
		font-size: 24rpx;
		font-weight: 900;
		color: #999999;
		margin-left: 452rpx;
	}
	.wechat{
		width: 650rpx;
		height: 121rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.wx{
		width: 70rpx;
		height: 70rpx;
		margin-left: 10rpx;
	}
	.wechat_payment{
		width: 242rpx;
		height: 70rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		margin-left: 20rpx;
	}
	.wechat_payment p{
		font-size: 24rpx;
		font-weight: 900;
	}
	.wechat_payment text{
		font-size: 20rpx;
		color: #999999;
		font-weight: 900;
	}
	.hook{
		width: 46rpx;
		height: 46rpx;
		margin-left: 250rpx;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 30rpx;
		font-weight: 900;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 80rpx;
	}
</style>