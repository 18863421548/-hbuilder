<template>
	<view class="whole">
		<view class="head">
			<p>备注：密码由6-20个英文字母，数字或者符号组成</p>
		</view>
		<view class="password">
			<view class="used_password">
				<p>原密码</p>
				<input type="text" placeholder="请输入原密码">
			</view>
			<view class="new_password">
				<p>新密码</p>
				<input type="text" placeholder="请输入新密码">
			</view>
			<view class="confirm_password">
				<p>确认密码</p>
				<input type="text" placeholder="再次输入新密码">
			</view>
		</view>
		<button class="but">完成</button>
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
		height: 63rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.head p{
		font-size: 24rpx;
	}
	.password{
		width: 690rpx;
		height: 260rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.used_password{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.used_password p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.used_password input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 86rpx;
	}
	
	.new_password{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.new_password p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.new_password input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 86rpx;
	}
	.confirm_password{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.confirm_password p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.confirm_password input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 60rpx;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		background-color: #ff6100;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		color: #fff;
		font-size: 28rpx;
		margin-top: 100rpx;
		font-weight: 900;
	}
</style>