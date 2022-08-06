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
				<image src="../../../../static/sm3.jpg" mode="" class="img3"></image>
			</view>
			<view class="process_bottom">
				<text class="text1">选择认证角色</text>
				<text class="text2">填写信息认证</text>
				<text class="text3">提交审核</text>
			</view>
		</view>
		<view class="face_recognition">
			<view class="yuan">
				<image src="../../../../static/人脸识别.jpg" mode=""></image>
			</view>
			<p>账户安全</p>
			<text>为了您的账号安全，请进行人脸识别验证</text>
		</view>
		<!-- 我已阅读并同意《用户个人信息授权协议》 -->
		<view class="agreement">
			<!-- 同意按钮 -->
			<u-checkbox-group>
				<u-checkbox v-model="checked" shape="square" label=""></u-checkbox>
			</u-checkbox-group>
			<text>我已阅读并同意<span class="download">《用户个人信息授权协议》</span></text>
		</view>
		<button class="but">开始验证</button>
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
		margin-left: 120rpx;
		display: block;
	}
	.text3{
		font-size: 24rpx;
		margin-left: 148rpx;
		display: block;
	}
	.face_recognition{
		width: 750rpx;
		height: 820rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.yuan{
		width: 284rpx;
		height: 284rpx;
		border-radius: 50%;
		background-color: #f6ece7;
		margin-top: 80rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.yuan image{
		width: 114rpx;
		height: 114rpx;
	}
	.face_recognition p{
		font-size: 28rpx;
		margin-top: 50rpx;
	}
	.face_recognition text{
		font-size: 24rpx;
		color: #999999;
		margin-top: 40rpx;
	}
	.agreement{
		width: 690rpx;
		height: 60rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.agreement text{
		font-size: 24rpx;
	}
	.download{
		color: #ff6100;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 28rpx;
		font-weight: 900;
	}
</style>