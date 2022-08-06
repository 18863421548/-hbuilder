<template>
	<view class="whole">
		<view class="account">
			<view class="head">
				<image src="../../../../static/zh1.jpg" mode="" class="img_left"></image>
				<p>头像</p>
				<image src="../../../../static/th.jpg" mode="" class="img_right"></image>
			</view>
			<view class="phone">
				<image src="../../../../static/zh2.jpg" mode="" class="img_left"></image>
				<p>绑定手机号</p>
				<text>17526408365</text>
				<span>修改</span>
			</view>
			<view class="news">
				<image src="../../../../static/zh3.jpg" mode="" class="img_left"></image>
				<p>接收消息/接收手机号</p>
				<text>17526408365</text>
				<span>修改</span>
			</view>
<!-- 			<view class="wechat">
				<image src="../../../../static/zh4.jpg" mode="" class="img_left"></image>
				<p>微信绑定</p>
				<text>微信用户</text>
			</view> -->
			<view class="password">
				<image src="../../../../static/zh5.jpg" mode="" class="img_left"></image>
				<p>登录密码</p>
				<text @click="modify">修改</text>
				<span @click="forget">忘记密码</span>
			</view>
			<view class="company">
				<image src="../../../../static/zh6.jpg" mode="" class="img_left"></image>
				<view class="company_content">
					<p>归属公司</p>
					<text>无</text>
				</view>
				<button>加入</button>
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
			// 修改
			modify(){
				uni.navigateTo({
					url:"./change_password"
				})
			},
			// 忘记密码
			forget(){
				uni.navigateTo({
					url:"./forget_password"
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
		overflow: hidden;
	}
	.account{
		width: 690rpx;
		height: 546rpx;
		margin: 0 auto;
		background-color: #fff;
		border-radius: 10px;
		margin-top: 20rpx;
	}
	.head{
		width: 650rpx;
		height: 87rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.img_left{
		width: 30rpx;
		height: 31rpx;
		margin-left: 10rpx;
	}
	.head p{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #999999;
	}
	.img_right{
		width: 60rpx;
		height: 60rpx;
		border-radius: 50%;
		margin-left: 458rpx;
	}
	.phone{
		width: 650rpx;
		height: 87rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.phone image{
		width: 30rpx;
		height: 31rpx;
		margin-left: 10rpx;
	}
	.phone p{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #999999;
	}
	.phone text{
		font-size: 26rpx;
		margin-left: 207rpx;
		color: #000;
	}
	.phone span{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #ff6100;
	}
	.news{
		width: 650rpx;
		height: 87rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.news image{
		width: 30rpx;
		height: 31rpx;
		margin-left: 10rpx;
	}
	.news p{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #999999;
	}
	.news text{
		font-size: 26rpx;
		margin-left: 92rpx;
		color: #000;
	}
	.news span{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #ff6100;
	}
	.wechat{
		width: 650rpx;
		height: 87rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.wechat image{
		width: 30rpx;
		height: 31rpx;
		margin-left: 10rpx;
	}
	.wechat p{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #999999;
	}
	.wechat text{
		font-size: 26rpx;
		margin-left: 365rpx;
		color: #000;
	}
	.password{
		width: 650rpx;
		height: 87rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.password image{
		width: 30rpx;
		height: 31rpx;
		margin-left: 10rpx;
	}
	.password p{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #999999;
	}
	.password text{
		font-size: 26rpx;
		margin-left: 293rpx;
		color: #ff6100;
	}
	.password span{
		font-size: 26rpx;
		margin-left: 20rpx;
		color: #ff6100;
	}
	.company{
		width: 650rpx;
		height: 104rpx;
		margin: 0 auto;
		display: flex;
	}
	.company image{
		width: 30rpx;
		height: 31rpx;
		margin-left: 10rpx;
		margin-top: 30rpx;
	}
	.company_content{
		width: 104rpx;
		height: 104rpx;
		display: flex;
		flex-direction: column;
		margin-left: 20rpx;
	}
	.company_content p{
		width: 104rpx;
		height: 52rpx;
		font-size: 26rpx;
		color: #999999;
		display: flex;
		align-items: center;
	}
	.company_content text{
		font-size: 26rpx;
		color: #000;
	}
	.company button{
		width: 120rpx;
		height: 50rpx;
		margin-left: 348rpx;
		margin-top: 30rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>