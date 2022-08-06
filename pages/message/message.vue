<template>
	<view>
		<view class="head"></view>
		<view class="name">
			<input type="text" placeholder="请输入您的名字">
		</view>
		<view class="contact_number">
			<input type="text" placeholder="请输入您的联系电话">
		</view>
		<view class="e_mail">
			<input type="text" placeholder="请输入您的电子邮箱">
		</view>
		<view class="message">
			<textarea placeholder="请输入您的留言内容..."></textarea>
		</view>
		<view class="but">
			<button>提交留言</button>
		</view>
		<view class="under">
			<view class="under_content">
				<view class="user" @click="userInstructions">
					<image src="../../static/ly1.jpg" mode=""></image>
					<text>用户须知</text>
				</view>
				<view class="standard" @click="standard">
					<image src="../../static/ly2.jpg" mode=""></image>
					<text>标准售后服务承诺</text>
				</view>
				<view class="common" @click="commonProblem">
					<image src="../../static/ly3.jpg" mode=""></image>
					<text>常见问题</text>
				</view>
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
			// 用户须知
			userInstructions(){
				uni.navigateTo({
					url:"./user_instructions"
				})
			},
			// 标准售后服务承诺
			standard(){
				uni.navigateTo({
					url:"./standard"
				})
			},
			// 常见问题
			commonProblem(){
				uni.navigateTo({
					url:"./common_problem"
				})
			}
		}
	}
</script>

<style>
	.head{
		width: 750rpx;
		height: 51rpx;
		background-color: #f9f9f9;
	}
	.name{
		width: 750rpx;
		height: 108rpx;
		background-color: #f9f9f9;
	}
	.name input{
		width: 670rpx;
		height: 88rpx;
		border: 1px solid #cccccc;
		border-radius: 5px;
		margin: 0 auto;
		font-size: 24rpx;
		color: #999999;
		padding-left: 20rpx;
	}
	.contact_number{
		width: 750rpx;
		height: 108rpx;
		background-color: #f9f9f9;
	}
	.contact_number input{
		width: 670rpx;
		height: 88rpx;
		border: 1px solid #cccccc;
		border-radius: 5px;
		margin: 0 auto;
		font-size: 24rpx;
		color: #999999;
		padding-left: 20rpx;
	}
	.e_mail{
		width: 750rpx;
		height: 108rpx;
		background-color: #f9f9f9;
	}
	.e_mail input{
		width: 670rpx;
		height: 88rpx;
		border: 1px solid #cccccc;
		border-radius: 5px;
		margin: 0 auto;
		font-size: 24rpx;
		color: #999999;
		padding-left: 20rpx;
	}
	.message{
		width: 750rpx;
		height: 310rpx;
		background-color: #f9f9f9;
	}
	.message textarea{
		width: 670rpx;
		height: 230rpx;
		border: 1px solid #cccccc;
		border-radius: 5px;
		margin: 0 auto;
		font-size: 24rpx;
		color: #999999;
		padding-left: 20rpx;
		padding-top: 30rpx;
	}
	.but{
		width: 750rpx;
		height: 408rpx;
		background-color: #f9f9f9;
	}
	.but button{
		width: 690rpx;
		height: 88rpx;
		background-color: #ff6100;
		color: #fff;
		margin: 0 auto;
		border-radius: 20px;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		font-weight: 900;
	}
	.under{
		width: 750rpx;
		height: 54rpx;
		background-color: #f9f9f9;
	}
	.under_content{
		width: 690rpx;
		height: 32rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.user{
		width: 145rpx;
		height: 32rpx;
		display: flex;
		justify-content: space-between;
	}
	.user image{
		width: 32rpx;
		height: 32rpx;
	}
	.user text{
		font-size: 24rpx;
		color: #999999;
	}
	.standard{
		width: 240rpx;
		height: 32rpx;
		display: flex;
		justify-content: space-between;
	}
	.standard image{
		width: 32rpx;
		height: 32rpx;
	}
	.standard text{
		font-size: 24rpx;
		color: #999999;
	}
	.common{
		width: 143rpx;
		height: 32rpx;
		display: flex;
		justify-content: space-between;
	}
	.common image{
		width: 32rpx;
		height: 32rpx;
	}
	.common text{
		font-size: 24rpx;
		color: #999999;
	}
</style>