<template>
	<view class="whole">
		<view class="head">
			<p>设备登记</p>
		</view>
		<view class="register">
			<view class="time">
				<p>登录时间</p>
				<input type="text" placeholder="请输入登记时间">
			</view>
			<view class="serial">
				<p>序列号</p>
				<input type="text" placeholder="请输入产品序列号">
			</view>
			<view class="repair">
				<p>维修原因</p>
				<input type="text" placeholder="请输入维修原因">
			</view>
			<view class="remarks">
				<p>备注</p>
				<input type="text" placeholder="非必填,可描述设备情况或您的要求">
			</view>
		</view>
		<view class="content">
			<p>联系人信息</p>
		</view>
		<view class="contacts">
			<view class="name">
				<p>联系人</p>
				<input type="text" placeholder="请输入联系人姓名">
			</view>
			<view class="telephone">
				<p>联系电话</p>
				<input type="text" placeholder="请输入联系电话">
			</view>
			<view class="convenient_time">
				<p>方便联系的时间</p>
				<input type="text" placeholder="非必填">
			</view>
		</view>
		<button class="but" @click="repairNext">下一步</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			repairNext(){
				uni.navigateTo({
					url:"./repair_next"
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
		width: 750rpx;
		height: 86rpx;
		overflow: hidden;
	}
	.head p{
		margin-top: 36rpx;
		margin-left: 30rpx;
		font-size: 26rpx;
		font-weight: 900;
	}
	.register{
		width: 690rpx;
		height: 355rpx;
		border-radius: 10px;
		margin: 0 auto;
		background-color: #fff;
	}
	.time{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.time p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.time input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.serial{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.serial p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.serial input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.repair{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.repair p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.repair input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.remarks{
		width: 650rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.remarks p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.remarks input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.content{
		width: 750rpx;
		height: 86rpx;
		overflow: hidden;
	}
	.content p{
		margin-top: 36rpx;
		margin-left: 30rpx;
		font-size: 26rpx;
		font-weight: 900;
	}
	.contacts{
		width: 690rpx;
		height: 266rpx;
		border-radius: 10px;
		margin: 0 auto;
		background-color: #fff;
	}
	.name{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.name p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.name input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.telephone{
		width: 650rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.telephone p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.telephone input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.convenient_time{
		width: 650rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.convenient_time p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.convenient_time input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #cccccc;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		background-color: #ff6100;
		font-size: 28rpx;
		color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 20px;
		margin-top: 325rpx;
	}
</style>