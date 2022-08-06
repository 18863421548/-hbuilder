<template>
	<view class="whole">
		<view class="name">
			<p>名称</p>
			<input type="text" placeholder="请输入标题名称">
		</view>
		<view class="image_upload">
			<p>图片上传</p>
			<text>图片上传：最多可以上传20张图片</text>
			<view class="imgas" @click="upload">
				<image src="../../../../static/信息.jpg" mode=""></image>
			</view>
		</view>
		<view class="remarks">
			<p>备注</p>
			<input type="text" placeholder="请输入您的备注内容...">
		</view>
		<button class="but">保存提交</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			// 图片上传
			upload(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
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
	.name{
		width: 750rpx;
		height: 88rpx;
		border-top: 1px solid #cccccc;
		background-color: #fff;
		display: flex;
		align-items: center;
	}
	.name p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.name input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 48rpx;
	}
	.image_upload{
		width: 750rpx;
		height: 309rpx;
		background-color: #fff;
		margin-top: 20rpx;
		overflow: hidden;
	}
	.image_upload p{
		font-size: 26rpx;
		margin-left: 30rpx;
		margin-top: 30rpx;
	}
	.image_upload text{
		font-size: 24rpx;
		color: #999999;
		margin-left: 30rpx;
		display: block;
		margin-top: 14rpx;
	}
	.imgas{
		width: 240rpx;
		height: 160rpx;
		border-radius: 10px;
		background-color: #f5f5f5;
		/* background-color: aqua; */
		margin-left: 30rpx;
		margin-top: 14rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.imgas image{
		width: 68rpx;
		height: 68rpx;
	}
	.remarks{
		width: 750rpx;
		height: 280rpx;
		background-color: #fff;
		margin-top: 20rpx;
		overflow: hidden;
	}
	.remarks p{
		margin-left: 30rpx;
		margin-top: 30rpx;
		font-size: 26rpx;
	}
	.remarks input{
		font-size: 24rpx;
		margin-left: 30rpx;
		color: #999999;
		margin-top: 10rpx;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		font-size: 28rpx;
		background-color: #ff6100;
		color: #fff;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 40rpx;
		margin-top: 400rpx;
		font-weight: 900;
	}
</style>