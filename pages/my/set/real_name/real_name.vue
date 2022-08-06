<template>
	<view class="whole">
		<view class="head">
			<p>为了保护您的账户安全，请先完成实名认证</p>
		</view>
		<view class="process">
			<view class="process_top">
				<image src="../../../../static/sm1.jpg" mode="" class="img1"></image>
				<view class="dotted_line"></view>
				<image src="../../../../static/sm2.jpg" mode="" class="img2"></image>
				<view class="dotted_line"></view>
				<image src="../../../../static/sm3.jpg" mode="" class="img3"></image>
			</view>
			<view class="process_bottom">
				<text class="text1">选择认证角色</text>
				<text class="text2">填写信息认证</text>
				<text class="text3">提交审核</text>
			</view>
		</view>
		<view class="authentication">
			<view class="authentication_left">
				<image src="../../../../static/sm4.jpg" mode=""></image>
				<p>我是个人</p>
				<view class="but" @click="personal">立即认证</view>
			</view>
			<view class="authentication_right">
				<image src="../../../../static/sm5.jpg" mode=""></image>
				<p>我是企业</p>
				<view class="but" @click="enterprise">立即认证</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			// 个人认证
			personal(){
				uni.navigateTo({
					url:"./personal_certification"
				})
			},
			// 企业认证
			enterprise(){
				uni.navigateTo({
					url:"./enterprise_authentication"
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
	.authentication{
		width: 690rpx;
		height: 345rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
		display: flex;
	}
	.authentication_left{
		width: 345rpx;
		height: 240rpx;
		margin-top: 60rpx;
		border-right: 1px solid #999999;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.authentication_left image{
		width: 90rpx;
		height: 68rpx;
		margin-top: 10rpx;
	}
	.authentication_left p{
		font-size: 24rpx;
		margin-top: 30rpx;
		font-weight: 900;
	}
	.but{
		width: 130rpx;
		height: 44rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 24rpx;
		margin-top: 38rpx;
		font-weight: 900;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 10rpx;
	}
	
	.authentication_right{
		width: 345rpx;
		height: 240rpx;
		margin-top: 60rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.authentication_right image{
		width: 90rpx;
		height: 80rpx;
		margin-top: 4rpx;
	}
	.authentication_right p{
		font-size: 24rpx;
		margin-top: 24rpx;
		font-weight: 900;
	}
</style>