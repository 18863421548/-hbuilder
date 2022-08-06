<template>
	<view class="whole">
		<view class="head">
			<image src="../../static/th1.jpg" mode="" class="img1"></image>
			<p>笔记本</p>
			<image src="../../static/th2.jpg" mode="" class="img2"></image>
		</view>
		<view class="body">
			<view class="body_left">
				<image src="../../static/th3.jpg" mode=""></image>
			</view>
			<view class="body_zhong">
				<p class="name">Think Pad X13</p>
				<text class="configure">i5-10|8G|25G|核显|13.3</text>
				<view class="price">
					<span>￥</span>
					<p>299</p>
					<text class="monthly">/月</text>
					<text class="original_price">原价¥359</text>
				</view>
				<text class="quantity">仅剩11台</text>
				<view class="progress_bar">
					<u-line-progress :percentage="11" :showText="false" height="8" inactiveColor="#ffdfcc" activeColor="#ff6100">
					</u-line-progress>
				</view>
			</view>
			<view class="body_right">
				<view class="but">
					马上抢
				</view>
			</view>
		</view>
		
		
		<view class="body">
			<view class="body_left">
				<image src="../../static/th3.jpg" mode=""></image>
			</view>
			<view class="body_zhong">
				<p class="name">Think Pad X13</p>
				<text class="configure">i5-10|8G|25G|核显|13.3</text>
				<view class="price">
					<span>￥</span>
					<p>299</p>
					<text class="monthly">/月</text>
					<text class="original_price">原价¥359</text>
				</view>
				<text class="quantity">仅剩11台</text>
				<view class="progress_bar">
					<u-line-progress :percentage="11" :showText="false" height="8" inactiveColor="#ffdfcc" activeColor="#ff6100">
					</u-line-progress>
				</view>
			</view>
			<view class="body_right">
				<view class="but">
					马上抢
				</view>
			</view>
		</view>
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
		width: 750rpx;
		height: 56rpx;
		display: flex;
		align-items: flex-end;
		justify-content: center;
		overflow: hidden;
	}
	.head image{
		width: 30rpx;
		height: 30rpx;
	}
	.img1{
		margin-right: 10rpx;
	}
	.img2{
		margin-left: 10rpx;
	}
	.head p{
		font-size: 26rpx;
		font-weight: 900;
	}
	.body{
		width: 690rpx;
		height: 246rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
		display: flex;
		align-items: center;
	}
	.body_left{
		width: 188rpx;
		height: 130rpx;
		margin-left: 40rpx;
	}
	.body_left image{
		width: 188rpx;
		height: 130rpx;
	}
	.body_zhong{
		width: 280rpx;
		height: 174rpx;
		margin-left: 36rpx;
	}
	.name{
		font-size: 26rpx;
		font-weight: 900;
	}
	.configure{
		font-size: 20rpx;
		display: block;
	}
	.price{
		width: 280rpx;
		height: 50rpx;
		display: flex;
		align-items: center;
	}
	.price span{
		font-size: 20rpx;
		font-weight: 900;
		color: #e81717;
	}
	.price p{
		font-size: 26rpx;
		font-weight: 900;
		color: #e81717;
	}
	.monthly{
		font-size: 20rpx;
		font-weight: 900;
		color: #e81717;
	}
	.original_price{
		text-decoration:line-through;
		font-size: 20rpx;
		margin-left: 8rpx;
	}
	.quantity{
		font-size: 20rpx;
		display: block;
	}
	.progress_bar{
		width: 190rpx;
		margin-top: 4rpx;
	}
	.body_right{
		width: 100rpx;
		height: 200rpx;
		margin-left: 2rpx;
	}
	.but{
		width: 100rpx;
		height: 40rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 20rpx;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		font-weight: 900;
		margin-top: 134rpx;
	}
</style>