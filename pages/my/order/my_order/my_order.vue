<template>
	<view class="whole">
		<view class="nav">
			<view class="nav_content">
				<view :class="activite==1?'bar':'index'" @click="ckeckIndex(1)">全部订单</view>
				<view :class="activite==2?'bar':'index'" @click="ckeckIndex(2)">初审中</view>
				<view :class="activite==3?'bar':'index'" @click="ckeckIndex(3)">复审中</view>
				<view :class="activite==4?'barr':'indexx'" @click="ckeckIndex(4)">合同签约</view>
			</view>
		</view>
		<!-- 初审中 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>初审中</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<view class="upload" @click="upload">上传征信资料</view>
				<view class="see">查看订单</view>
				<view class="cancel">取消订单</view>
			</view>
		</view>
		<view class="asd" v-show="activite==2">
			<view class="all_order">
				<view class="head">
					<view class="heads">
						<view class="head_content">
							<p>订单号</p>
							<text>2011061410254891002</text>
						</view>
						<span>初审中</span>
					</view>
				</view>
				<view class="body">
					<view class="body_left">
						<image src="../../../../static/cp1.jpg" mode=""></image>
					</view>
					<view class="body_right">
						<view class="body_right_name">
							<p>随用随还</p>
							<text>
							苹果 (Apple) MacBook Pro 
							2019 Z0XZ 16英寸笔记本电脑(G5905 
							双核/8G/256G SSD)	
							</text>
						</view>
						<view class="body_right_time">
							<p>服务期：2022-06-17至2025-06-16</p>
							<text>×1</text>
						</view>
						<view class="body_right_price">
							<p>￥21200</p>
						</view>
					</view>
				</view>
				<view class="leg">
					<view class="upload" @click="upload">上传征信资料</view>
					<view class="see">查看订单</view>
					<view class="cancel">取消订单</view>
				</view>
			</view>
		</view>
		<!-- 复审中 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>复审中</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<view class="upload" @click="upload">查看征信资料</view>
				<view class="see">查看订单</view>
				<view class="cancel">取消订单</view>
			</view>
		</view>
		<view class="asd" v-show="activite==3">
			<view class="all_order">
				<view class="head">
					<view class="heads">
						<view class="head_content">
							<p>订单号</p>
							<text>2011061410254891002</text>
						</view>
						<span>复审中</span>
					</view>
				</view>
				<view class="body">
					<view class="body_left">
						<image src="../../../../static/cp1.jpg" mode=""></image>
					</view>
					<view class="body_right">
						<view class="body_right_name">
							<p>随用随还</p>
							<text>
							苹果 (Apple) MacBook Pro 
							2019 Z0XZ 16英寸笔记本电脑(G5905 
							双核/8G/256G SSD)	
							</text>
						</view>
						<view class="body_right_time">
							<p>服务期：2022-06-17至2025-06-16</p>
							<text>×1</text>
						</view>
						<view class="body_right_price">
							<p>￥21200</p>
						</view>
					</view>
				</view>
				<view class="leg">
					<view class="upload" @click="upload">查看征信资料</view>
					<view class="see">查看订单</view>
					<view class="cancel">取消订单</view>
				</view>
			</view>
		</view>
		<!-- 合同签约 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>合同签约</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<!-- <view class="see_second" @click="order_details">查看订单</view> -->
				<view class="signing">签约合同</view>
				<view class="see">查看订单</view>
				<view class="cancel">取消订单</view>
			</view>
		</view>
		<view class="asd"  v-show="activite==4">
			<view class="all_order">
				<view class="head">
					<view class="heads">
						<view class="head_content">
							<p>订单号</p>
							<text>2011061410254891002</text>
						</view>
						<span>合同签约</span>
					</view>
				</view>
				<view class="body">
					<view class="body_left">
						<image src="../../../../static/cp1.jpg" mode=""></image>
					</view>
					<view class="body_right">
						<view class="body_right_name">
							<p>随用随还</p>
							<text>
							苹果 (Apple) MacBook Pro 
							2019 Z0XZ 16英寸笔记本电脑(G5905 
							双核/8G/256G SSD)	
							</text>
						</view>
						<view class="body_right_time">
							<p>服务期：2022-06-17至2025-06-16</p>
							<text>×1</text>
						</view>
						<view class="body_right_price">
							<p>￥21200</p>
						</view>
					</view>
				</view>
				<view class="leg">
					<!-- <view class="see_second" @click="order_details">查看订单</view> -->
					<view class="signing">签约合同</view>
					<view class="see">查看订单</view>
					<view class="cancel">取消订单</view>
				</view>
			</view>
		</view>
		<!-- 待配送 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>待配送</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<view class="see_second" @click="order_details">查看订单</view>
				<view class="confirm">确认收货</view>
			</view>
		</view>
		<!-- 租赁中 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>租赁中</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<view class="see_second">查看订单</view>
				<view class="rent_withdrawal">退租回收</view>
			</view>
		</view>
		<!-- 待回收 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>待回收</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<!-- <view class="see_second" @click="order_details">查看订单</view> -->
				<view class="signing">退租回收</view>
				<view class="see">查看订单</view>
				<view class="cancel">订单续约</view>
			</view>
		</view>
		<!-- 待结算 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>待回收</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<p>丢损费：¥256</p>
				<view class="see">查看订单</view>
				<view class="cancel">订单续约</view>
			</view>
		</view>
		<!-- 已完成 -->
		<view class="all_order" v-show="activite==1">
			<view class="head">
				<view class="heads">
					<view class="head_content">
						<p>订单号</p>
						<text>2011061410254891002</text>
					</view>
					<span>待回收</span>
				</view>
			</view>
			<view class="body">
				<view class="body_left">
					<image src="../../../../static/cp1.jpg" mode=""></image>
				</view>
				<view class="body_right">
					<view class="body_right_name">
						<p>随用随还</p>
						<text>
						苹果 (Apple) MacBook Pro 
						2019 Z0XZ 16英寸笔记本电脑(G5905 
						双核/8G/256G SSD)	
						</text>
					</view>
					<view class="body_right_time">
						<p>服务期：2022-06-17至2025-06-16</p>
						<text>×1</text>
					</view>
					<view class="body_right_price">
						<p>￥21200</p>
					</view>
				</view>
			</view>
			<view class="leg">
				<view class="see_second">查看订单</view>
				<view class="rent_withdrawal">删除订单</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data(){
			return{
				activite:1,
			}
		},
		methods:{
			ckeckIndex(e){
				this.activite=e
			},
			// 上传征信资料
			upload(){
				uni.navigateTo({
					url:"./upload_credit_information"
				})
			},
			// 订单详情 待配送的
			order_details(){
				uni.navigateTo({
					url:"./order_details"
				})
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 100%;
		background-color: #f5f5f5;
		overflow: hidden;
	}
	.nav{
		width: 750rpx;
		height: 100rpx;
		background-color: #f5f5f5;
		display: flex;
		align-items: center;
		overflow: hidden;
	}
	.nav_content{
		width: 750rpx;
		height: 80rpx;
		margin-top: 20rpx;
		display: flex;
		align-items: center;
	}
	.bar{
		width: 150rpx;
		height: 60rpx;
		border-radius: 30rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-left: 30rpx;
	}
	.index{
		width: 150rpx;
		height: 60rpx;
		border-radius: 30rpx;
		background-color: #fff;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-left: 30rpx;
	}
	.barr{
		width: 174rpx;
		height: 60rpx;
		border-radius: 30rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-left: 30rpx;
	}
	.indexx{
		width: 174rpx;
		height: 60rpx;
		border-radius: 30rpx;
		background-color: #fff;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-left: 30rpx;
	}
	.all_order{
		width: 690rpx;
		height: 443rpx;
		border-radius: 10px;
		background-color: #fff;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.head{
		width: 690rpx;
		height: 66rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
		font-size: 26rpx;
	}
	.heads{
		width: 650rpx;
		height: 66rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-size: 26rpx;
	}
	.head_content{
		width: 410rpx;
		display: flex;
	}
	.head_content p{
		
	}
	.head_content text{
		margin-left: 9rpx;
	}
	.heads span{
		color: #ff6100;
	}
	.body{
		width: 690rpx;
		height: 257rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
	}
	.body_left{
		width: 187rpx;
		height: 257rpx;
	}
	.body_left image{
		width: 138rpx;
		height: 79rpx;
		margin-top: 50rpx;
		margin-left: 30rpx;
	}
	.body_right{
		width: 504rpx;
		height: 257rpx;
		/* background-color: aqua; */
		display: flex;
		flex-direction: column;
	}
	.body_right_name{
		width: 442rpx;
		height: 99rpx;
		margin-top: 30rpx;
	}
	.body_right_name p{
		background-color: #e81717;
		color: #fff;
		width: 110rpx;
		height: 34rpx;
		border-radius: 40rpx;
		font-size: 22rpx;
		position: absolute;
		text-align: center;
	}
	.body_right_name text{
		display: block;
		text-indent: 118rpx;
		font-size: 24rpx;
		font-weight: 900;
	}
	
	.body_right_time{
		width: 474rpx;
		height: 76rpx;
		display: flex;
		justify-content: space-between;
	}
	.body_right_time p{
		font-size: 22rpx;
		color: #999999;
		margin-top: 31rpx;
	}
	.body_right_time text{
		font-size: 26rpx;
		font-weight: 900;
		margin-top: 26rpx;
	}
	.body_right_price{
		width: 200rpx;
		height: 52rpx;
		/* background-color: blueviolet; */
	}
	.body_right_price p{
		font-size: 26rpx;
		color: #e81717;
		font-weight: 900;
	}
	
	.leg{
		width: 690rpx;
		height: 120rpx;
		display: flex;
		align-items: center;
	}
	.leg p{
		width: 270rpx;
		font-size: 26rpx;
		color: #999999;
		margin-left: 30rpx;
	}
	.upload{
		width: 200rpx;
		height: 60rpx;
		border-radius: 40rpx;
		border: 1px solid #ff6100;
		background-color: #fff;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 98rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.see{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #fff;
		border: 1px solid #ff6100;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 30rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.cancel{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #fff;
		border: 1px solid #ff6100;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 28rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.signing{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #fff;
		border: 1px solid #ff6100;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 144rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.confirm{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #fff;
		border: 1px solid #ff6100;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 30rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
	
	/* .all_order_second{
		width: 690rpx;
		height: 443rpx;
		border-radius: 10px;
		background-color: #fff;
		margin: 0 auto;
		margin-top: 20rpx;
	} */
	.see_second{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #fff;
		border: 1px solid #ff6100;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 330rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.rent_withdrawal{
		width: 150rpx;
		height: 60rpx;
		border-radius: 40rpx;
		background-color: #fff;
		border: 1px solid #ff6100;
		color: #ff6100;
		font-size: 26rpx;
		margin-left: 30rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.asd{
		width: 100%;
		height: 1146rpx;
		background-color: #f5f5f5;
		overflow: hidden;
	}
</style>