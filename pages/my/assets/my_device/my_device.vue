<template>
	<view class="whole">
		<view class="head">
			<view class="head_content">
				<view class="head_content_top">
					<view class="head_content_top_left">
						<image src="../../../../static/sb1.jpg" mode=""></image>
						<view class="words" @click="leasedEquipment">
							<p>在租设备 (台)</p>
							<text>103</text>
						</view>
					</view>
					<view class="head_content_top_right">
						<image src="../../../../static/向右箭头.png" mode=""></image>
					</view>
				</view>
				<view class="head_content_bottom">
					<view class="head_content_bottom_left">
						<image src="../../../../static/sb2.jpg" mode=""></image>
						<view class="words">
							<p>退租设备 (台)</p>
							<text>263</text>
						</view>
					</view>
					<view class="head_content_bottom_right">
						<image src="../../../../static/向右箭头.png" mode=""></image>
					</view>
				</view>
			</view>
		</view>
		<view class="bottom_tips">
			<text>设备回收及退租，请到悟空优租服务-还机服务查找</text>
			<text>批量导入，导出功能，请前往网页端操作</text>
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
			// 在租设备
			leasedEquipment(){
				uni.navigateTo({
					url:"./leased_equipment"
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
	.head{
		width: 750rpx;
		height: 362rpx;
		background: linear-gradient(#ff6608, #f5f5f5);
		overflow: hidden;
	}
	.head_content{
		width: 690rpx;
		height: 322rpx;
		background-color: #ffffff;
		margin: 0 auto;
		border-radius: 10px;
		margin-top: 40rpx;
	}
	.head_content_top{
		width: 610rpx;
		height: 161rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.head_content_top_left{
		width: 290rpx;
		height: 80rpx;
		display: flex;
	}
	.head_content_top_left image{
		width: 80rpx;
		height: 80rpx;
	}
	.words{
		width: 180rpx;
		height: 80rpx;
		margin-left: 30rpx;
	}
	.words p{
		font-size: 26rpx;
		color: #999999;
	}
	.words text{
		font-size: 26rpx;
	}
	.head_content_top_right image{
		width: 20rpx;
		height: 26rpx;
	}
	
	
	
	.head_content_bottom{
		width: 610rpx;
		height: 161rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.head_content_bottom_left{
		width: 290rpx;
		height: 80rpx;
		display: flex;
	}
	.head_content_bottom_left image{
		width: 80rpx;
		height: 80rpx;
	}
	.head_content_bottom_right image{
		width: 20rpx;
		height: 26rpx;
	}
	.bottom_tips{
		width: 690rpx;
		height: 75rpx;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
		margin-top: 730rpx;
	}
	.bottom_tips text{
		font-size: 24rpx;
		color: #999999;
	}
</style>