<template>
	<view>
		<view class="head">
			<view class="head_content">
				<p>服务单号 WX20220603536</p>
				<p>申请日期 2022.06.16</p>
			</view>
		</view>
		<view class="application_progress">
			<p>申请进度</p>
			<text>处理中</text>
		</view>
		<view class="state">
			<image src="../../../../static/yywx1.jpg" mode=""></image>
			<view class="state_content">
				<view class="xian"></view>
				<view class="yuan"></view>
				<view class="xian"></view>
			</view>
			<image src="../../../../static/yywx2.jpg" mode=""></image>
		</view>
		<view class="words">
			<text class="success">提交成功</text>
			<text class="close">服务关闭</text>
		</view>
		<view class="time">
			<view class="circumference">
				<view class="circular_heart">
				</view>
			</view>
			<p>06/16 14:25</p>
		</view>
		<view class="processing">
			<p>处理中</p>
			<text>您的维修服务申请已提交成功，正在处理中</text>
		</view>
		<view class="application_details">
			<p>申请单详情</p>
		</view>
		<view class="maintenance_reason">
			<p>维修原因</p>
			<text>电脑开不了机了</text>
		</view>
		<view class="contacts">
			<p>联系人</p>
			<text>李木子</text>
		</view>
		<view class="contact_number">
			<p>联系电话</p>
			<text>17526408365</text>
		</view>
		<view class="convenient_contact_time">
			<p>方便联系时间</p>
		</view>
		<view class="number_of_applied_equipment">
			<p>申请设备数量</p>
			<text>1</text>
		</view>
		<view class="withdraw">
			<button>取消申请</button>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.head{
		width: 750rpx;
		height: 132rpx;
		border-top: 1px solid #cccccc;
	}
	.head_content{
		width: 690rpx;
		height: 132rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.head_content p{
		font-size: 22rpx;
		font-weight: 900;
		margin-top: 30rpx;
	}
	.application_progress{
		width: 690rpx;
		height: 110rpx;
		margin: 0 auto;
	}
	.application_progress p{
		font-size: 26rpx;
		font-weight: 900;
	}
	.application_progress text{
		font-size: 20rpx;
		color: #ff6100;
		position: absolute;
		left: 340rpx;
		top: 220rpx;
	}
	.state{
		width: 390rpx;
		height: 40rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.state image{
		width: 40rpx;
		height: 40rpx;
	}
	.state_content{
		width: 270rpx;
		height: 10rpx;
		display: flex;
		align-items: center;
	}
	.xian{
		width: 130rpx;
		height: 2rpx;
		background-color: #ff6100;
	}
	.yuan{
		width: 10rpx;
		height: 10rpx;
		border-radius: 50%;
		background-color: #ff6100;
	}
	.words{
		width: 450rpx;
		height: 124rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.success{
		font-size: 24rpx;
		color: #ff6100;
		font-weight: 900;
		margin-top: 20rpx;
	}
	.close{
		font-size: 24rpx;
		color: #cccccc;
		font-weight: 900;
		margin-top: 20rpx;
	}
	.time{
		width: 690rpx;
		height: 38rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.circumference{
		width: 24rpx;
		height: 24rpx;
		border-radius: 50%;
		background-color: #ff6100;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-left: 30rpx;
	}
	.circular_heart{
		width: 12rpx;
		height: 12rpx;
		border-radius: 50%;
		background-color: #fff;
	}
	.time p{
		font-size: 24rpx;
		color: #999999;
		margin-left: 20rpx;
	}
	.processing{
		width: 619rpx;
		height: 100rpx;
		background-color: #ffefe5;
		border-radius: 10px;
		margin-top: 16rpx;
		margin-left: 100rpx;
		overflow: hidden;
	}
	.processing p{
		font-size: 26rpx;
		font-weight: 900;
		margin-left: 20rpx;
		margin-top: 16rpx;
	}
	.processing text{
		font-size: 22rpx;
		margin-left: 20rpx;
		display: block;
	}
	.application_details{
		width: 690rpx;
		height: 66rpx;
		margin: 0 auto;
		margin-top: 80rpx;
		display: flex;
		align-items: center;
	}
	.application_details p{
		font-size: 26rpx;
		font-weight: 900;
	}
	/* 维修原因 */
	.maintenance_reason{
		width: 750rpx;
		height: 90rpx;
		border-bottom: 1px solid #999999;
		display: flex;
		align-items: center;
	}
	.maintenance_reason p{
		font-size: 26rpx;
		color: #999999;
		margin-left: 30rpx;
	}
	.maintenance_reason text{
		font-size: 26rpx;
		margin-left: 50rpx;
	}
	/* 联系人 */
	.contacts{
		width: 750rpx;
		height: 90rpx;
		border-bottom: 1px solid #999999;
		display: flex;
		align-items: center;
	}
	.contacts p{
		font-size: 26rpx;
		color: #999999;
		margin-left: 30rpx;
	}
	.contacts text{
		font-size: 26rpx;
		margin-left: 50rpx;
	}
	/* 联系电话 */
	.contact_number{
		width: 750rpx;
		height: 90rpx;
		border-bottom: 1px solid #999999;
		display: flex;
		align-items: center;
	}
	.contact_number p{
		font-size: 26rpx;
		color: #999999;
		margin-left: 30rpx;
	}
	.contact_number text{
		font-size: 26rpx;
		margin-left: 50rpx;
	}
	/* 方便联系时间 */
	.convenient_contact_time{
		width: 750rpx;
		height: 90rpx;
		border-bottom: 1px solid #999999;
		display: flex;
		align-items: center;
	}
	.convenient_contact_time p{
		font-size: 26rpx;
		color: #999999;
		margin-left: 30rpx;
	}
	
	/* 申请设备数量 */
	.number_of_applied_equipment{
		width: 750rpx;
		height: 303rpx;
		border-bottom: 1px solid #999999;
		display: flex;
	}
	.number_of_applied_equipment p{
		font-size: 26rpx;
		color: #999999;
		margin-left: 30rpx;
		margin-top: 32rpx;
	}
	.number_of_applied_equipment text{
		font-size: 26rpx;
		margin-left: 50rpx;
		margin-top: 32rpx;
	}
	.withdraw{
		width: 750rpx;
		height: 190rpx;
	}
	.withdraw button{
		width: 175rpx;
		height: 70rpx;
		border-radius: 40rpx;
		border: 1px solid #999999;
		font-size: 28rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 22rpx;
		margin-left: 545rpx;
	}
</style>