<template>
	<view class="whole">
		<view class="head">
			<p>为了保护您的账户安全，请先完成实名认证</p>
		</view>
		<view class="process">
			<view class="process_top">
				<image src="../../../../static/sm1.jpg" mode="" class="img1"></image>
				<view class="dotted_line"></view>
				<image src="../../../../static/sm6.jpg" mode="" class="img2"></image>
				<view class="dotted_line"></view>
				<image src="../../../../static/sm7.jpg" mode="" class="img3"></image>
			</view>
			<view class="process_bottom">
				<text class="text1">选择认证角色</text>
				<text class="text2">填写信息认证</text>
				<text class="text3">提交审核</text>
			</view>
		</view>
		<view class="state1">
			<image src="../../../../static/审核中.jpg" mode=""></image>
			<p>正在加速审核中，请耐心等待</p>
			<text>客服热线：0531-8697114</text>
		</view>
		<!-- <view class="state2">
			<image src="../../../../static/已通过.jpg" mode=""></image>
			<p>您好，恭喜您您的实名审核已通过！</p>
		</view> -->
		<!-- <view class="state3">
			<image src="../../../../static/未通过.jpg" mode=""></image>
			<p>您好，很抱歉您的实名审核未通过</p>
			<text>查看原因</text>
			<view class="again">
				重新实名认证
			</view>
		</view> -->
	</view>
</template>

<script>
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #f5f5f5;
	}
	.head{
		width: 690rpx;
		height: 66rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.head p{
		font-size: 26rpx;
		color: #999999;
	}
	.process{
		width: 690rpx;
		height: 160rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.process_top{
		width: 690rpx;
		height: 100rpx;
		display: flex;
	}
	.img1{
		width: 60rpx;
		height: 60rpx;
		margin-top: 24rpx;
		margin-left: 56rpx;
	}
	.dotted_line{
		width: 200rpx;
		height: 2rpx;
		border-bottom: 1px dashed #999999;
		margin-left: 4rpx;
		margin-top: 54rpx;
	}
	.img2{
		width: 60rpx;
		height: 60rpx;
		margin-top: 24rpx;
		margin-left: 4rpx;
	}
	.img3{
		width: 60rpx;
		height: 60rpx;
		margin-top: 24rpx;
		margin-left: 4rpx;
	}
	.process_bottom{
		width: 690rpx;
		height: 50rpx;
		display: flex;
	}
	.text1{
		font-size: 24rpx;
		color: #ff6100;
		margin-left: 16rpx;
		display: block;
	}
	.text2{
		font-size: 24rpx;
		color: #ff6100;
		margin-left: 120rpx;
		display: block;
	}
	.text3{
		font-size: 24rpx;
		color: #ff6100;
		margin-left: 148rpx;
		display: block;
	}
	/* 审核中 */
	.state1{
		width: 750rpx;
		height: 800rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.state1 image{
		width: 198rpx;
		height: 193rpx;
		margin-top: 120rpx;
	}
	.state1 p{
		font-size: 28rpx;
		margin-top: 60rpx;
	}
	.state1 text{
		font-size: 24rpx;
		color: #ff6100;
		margin-top: 20rpx;
	}
	/* 已通过 */
	.state2{
		width: 750rpx;
		height: 800rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.state2 image{
		width: 158rpx;
		height: 192rpx;
		margin-top: 120rpx;
	}
	.state2 p{
		font-size: 28rpx;
		margin-top: 60rpx;
	}
	/* 未通过 */
	.state3{
		width: 750rpx;
		height: 800rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.state3 image{
		width: 185rpx;
		height: 192rpx;
		margin-top: 120rpx;
	}
	.state3 p{
		font-size: 28rpx;
		margin-top: 60rpx;
	}
	.state3 text{
		font-size: 24rpx;
		color: #ff6100;
		margin-top: 20rpx;
	}
	.again{
		width: 230rpx;
		height: 50rpx;
		background-color: #ff6100;
		border-radius: 10rpx;
		font-size: 24rpx;
		color: #fff;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 50rpx;
	}
</style>