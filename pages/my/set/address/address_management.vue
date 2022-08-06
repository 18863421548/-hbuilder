<template>
	<view class="whole">
		<view class="address_one">
			<view class="address_one_top">
				<view class="name">
					<p>李木子</p>
					<text>175****8365</text>
				</view>
				<view class="address">
					<text>山东 济南市历下区建新街道花园庄小区15号楼5单元202室</text>
				</view>
			</view>
			<view class="address_one_bottom">
				<u-checkbox-group>
					<u-checkbox v-model="checked" shape="circle" activeColor="#ff6100" checked="true"></u-checkbox>
				</u-checkbox-group>
				<text>设为默认地址</text>
				<view class="delete">
					<image src="../../../../static/删除.jpg" mode=""></image>
					<p>删除</p>
				</view>
				<view class="edit">
					<image src="../../../../static/编辑.jpg" mode=""></image>
					<p>编辑</p>
				</view>
			</view>
		</view>
		<button class="but" @click="newlyAdded">添加新地址</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			// 添加新地址    跳转到新增收货地址
			newlyAdded(){
				uni.navigateTo({
					url:"./add_receiving_address"
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
	.address_one{
		width: 690rpx;
		height: 263rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.address_one_top{
		width: 630rpx;
		height: 154rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
	}
	.name{
		display: flex;
	}
	.name p{
		font-size: 32rpx;
		margin-top: 40rpx;
	}
	.name text{
		font-size: 32rpx;
		margin-left: 22rpx;
		margin-top: 40rpx;
	}
	.address{
		
	}
	.address text{
		color: #999999;
		font-size: 24rpx;
		display: block;
		margin-top: 18rpx;
	}
	.address_one_bottom{
		width: 630rpx;
		height: 108rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.address_one_bottom text{
		font-size: 24rpx;
		color: #999999;
	}
	.delete{
		width: 93rpx;
		height: 35rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-left: 210rpx;
	}
	.delete image{
		width: 35rpx;
		height: 33rpx;
	}
	.delete p{
		font-size: 24rpx;
		color: #999999;
	}
	.edit{
		width: 93rpx;
		height: 35rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-left: 40rpx;
	}
	.edit image{
		width: 35rpx;
		height: 33rpx;
	}
	.edit p{
		font-size: 24rpx;
		color: #999999;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 30rpx;
		font-weight: 900;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 840rpx;
	}
</style>