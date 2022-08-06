<template>
	<view class="whole">
		<view class="head">
			<p @click="applyInvoice">申请发票</p>
		</view>
		<view class="body" v-for="item in list" @click="clickDetails">
			<view class="body_top">
				<p>申请时间：{{item.time}}</p>
				<view class="state">
					<text>{{item.state}}</text>
					<image src="../../../../static/向右箭头.png" mode=""></image>
				</view>
			</view>
			<view class="body_middle">
				<p>{{item.price}}</p>
				<text>{{item.type}} | 畅移（上海）信息科技</text>
			</view>
			<view class="body_bottom">
				<p>收票人：{{item.name}}</p>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				list:[
					{
						time:"2022-06-08",
						state:"审核中",
						price:"¥13907.5",
						type:"增值税专用发票",
						name:"王萌萌",
					},
					{
						time:"2022-06-08",
						state:"已开票",
						price:"¥13907.5",
						type:"增值税专用发票",
						name:"王萌萌",
					},
					{
						time:"2022-06-08",
						state:"审核未通过",
						price:"¥13907.5",
						type:"增值税专用发票",
						name:"王萌萌",
					},
					{
						time:"2022-06-08",
						state:"已开票",
						price:"¥13907.5",
						type:"增值税专用发票",
						name:"王萌萌",
					},
					{
						time:"2022-06-08",
						state:"已开票",
						price:"¥13907.5",
						type:"增值税专用发票",
						name:"王萌萌",
					},
					{
						time:"2022-06-08",
						state:"已开票",
						price:"¥13907.5",
						type:"增值税专用发票",
						name:"王萌萌",
					}
				]
			}
		},
		methods:{
			// 申请发票
			applyInvoice(){
				uni.navigateTo({
					url:"./invoice_information"
				})
			},
			// 点击去往发票详情
			clickDetails(){
				uni.navigateTo({
					url:"./invoice_details"
				})
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		background-color: #f5f5f5;
	}
	.head{
		width: 690rpx;
		height: 68rpx;
		margin: 0 auto;
		display: flex;
		/* align-items: center; */
		justify-content: flex-end;
	}
	.head p{
		margin-top: 24rpx;
		font-size: 28rpx;
		color: #ff6100;
	}
	.body{
		width: 690rpx;
		height: 190rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
		overflow: hidden;
		/* display: flex;
		flex-direction: column;
		justify-content: space-around; */
	}
	.body_top{
		width: 652rpx;
		height: 32rpx;
		margin: 0 auto;
		margin-top: 26rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.body_top p{
		font-size: 26rpx;
	}
	.state{
		height: 32rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.state text{
		font-size: 26rpx;
		display: block;
	}
	.state image{
		margin-top: 2rpx;
		width: 22rpx;
		height: 20rpx;
	}
	.body_middle{
		width: 652rpx;
		height: 30rpx;
		margin: 0 auto;
		margin-top: 22rpx;
		display: flex;
	}
	.body_middle p{
		font-size: 24rpx;
	}
	.body_middle text{
		margin-left: 20rpx;
		font-size: 24rpx;
		color: #999999;
	}
	.body_bottom{
		width: 652rpx;
		height: 30rpx;
		margin: 0 auto;
		margin-top: 22rpx;
	}
	.body_bottom p{
		font-size: 24rpx;
		color: #999999;
	}
</style>