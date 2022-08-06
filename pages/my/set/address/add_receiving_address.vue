<template>
	<view class="whole">
		<view class="body">
			<view class="name">
				<p>姓名</p>
				<input type="text" placeholder="收货人姓名">
			</view>
			<view class="phone">
				<p>手机号</p>
				<input type="text" placeholder="收件人手机号">
			</view>
			<view class="address">
				<p>所在地址</p>
				<input type="text" placeholder="选择收货地区">
				<view class="location">
					<u-icon name="map" color="#999999" size="14"></u-icon>
					<u-tag text="定位" size="mini" color="#999999" plain borderColor="#fff"></u-tag>
				</view>
			</view>
			<view class="detailed_address">
				<p>详细地址</p>
				<input type="text" placeholder="需要具体到街道、小区、门牌号等">
			</view>
		</view>
		<view class="default">
			<u-checkbox-group>
				<u-checkbox v-model="checked" shape="circle"></u-checkbox>
			</u-checkbox-group>
			<p>设为默认地址</p>
		</view>
		<button class="but">保存</button>
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
	.body{
		width: 690rpx;
		height: 397rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.name{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.name p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.name input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 100rpx;
	}
	.phone{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.phone p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.phone input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 74rpx;
	}
	.address{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.address p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.address input{
		width: 385rpx;
		font-size: 26rpx;
		color: #999999;
		margin-left: 48rpx;
	}
	.location{
		display: flex;
	}
	.detailed_address{
		width: 650rpx;
		height: 136rpx;
		margin: 0 auto;
		display: flex;
	}
	.detailed_address p{
		font-size: 26rpx;
		margin-left: 10rpx;
		margin-top: 30rpx;
	}
	.detailed_address input{
		width: 400rpx;
		font-size: 26rpx;
		color: #999999;
		margin-left: 48rpx;
		margin-top: 30rpx;
	}
	.default{
		width: 690rpx;
		height: 64rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.default p{
		font-size: 24rpx;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 30rpx;
		font-weight: 900;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 640rpx;
	}
</style>