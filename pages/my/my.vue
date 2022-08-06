<template>
	<view>
		<view class="header">
			<view class="header_content">
				<view class="portrait">
					<image :src="userInfo.avatar" mode=""></image>
				</view>
				<view class="telephone">
					<p>{{userInfo.uid}}</p>
					<text>未实名认证 > ></text>
				</view>
				<view class="set">
					<image src="../../static/205设置.png" mode=""></image>
				</view>
			</view>
		</view>
		<view class="neck">
			<view class="neck_content">
				<image src="../../static/个人中心.jpg" mode="" class="shield"></image>
				<view class="neck_words">
					<p>账户进行实名认证</p>
					<text>企业认证可获得5万保证金</text>
				</view>
				<image src="../../static/向右箭头.png" mode="" class="arrow"></image>
			</view>
		</view>
		<view class="order">
			<view class="order_content">
				<view class="order_content_head">
					<p>订单中心</p><image src="../../static/圆圈.jpg" mode=""></image>
				</view>
				<view class="order_content_body">
					<view class="my_order" @click="myOrder">
						<image src="../../static/dd1.jpg" mode=""></image>
						<p>我的订单</p>
					</view>
					<view class="renewal_order" @click="renewalOrder">
						<image src="../../static/dd2.jpg" mode=""></image>
						<p>续租订单</p>
					</view>
				</view>
			</view>
		</view>
		<view class="assets">
			<view class="assets_content">
				<view class="assets_content_head">
					<p>资产中心</p><image src="../../static/圆圈.jpg" mode=""></image>
				</view>
				<view class="assets_content_body">
					<view class="my_account" @click="myAccount">
						<image src="../../static/zc1.jpg" mode=""></image>
						<p>我的账户</p>
					</view>
					<view class="my_bill" @click="myBill">
						<image src="../../static/zc2.jpg" mode=""></image>
						<p>我的账单</p>
					</view>
					<view class="my_device" @click="myDevice">
						<image src="../../static/zc3.jpg" mode=""></image>
						<p>我的设备</p>
					</view>
					<view class="deposit_free" @click="depositFree">
						<image src="../../static/zc4.jpg" mode=""></image>
						<p>免押金额度</p>
					</view>
					<view class="my_coupons" @click="myCoupons">
						<image src="../../static/zc5.jpg" mode=""></image>
						<p>我的优惠券</p>
					</view>
				</view>
			</view>
		</view>
		<view class="service">
			<view class="service_content">
				<view class="service_content_head">
					<p>服务中心</p><image src="../../static/圆圈.jpg" mode=""></image>
				</view>
				<view class="service_content_body">
					<view class="invoice_information" @click="myInvoice">
						<image src="../../static/fw1.jpg" mode=""></image>
						<p>发票信息</p>
					</view>
					<view class="appointment_maintenance" @click="repair">
						<image src="../../static/fw2.jpg" mode=""></image>
						<p>预约维修</p>
					</view>
					<view class="rent_withdrawal">
						<image src="../../static/fw3.jpg" mode=""></image>
						<p>退租服务</p>
					</view>
					<view class="exchange_service">
						<image src="../../static/fw4.jpg" mode=""></image>
						<p>换货服务</p>
					</view>
				</view>
			</view>
		</view>
		<view class="set_up">
			<view class="set_up_content">
				<view class="set_up_content_head">
					<p>设置</p><image src="../../static/圆圈.jpg" mode=""></image>
				</view>
				<view class="set_up_content_body">
					<view class="account_security" @click="account">
						<image src="../../static/sz1.jpg" mode=""></image>
						<p>账户安全</p>
					</view>
					<view class="real_name" @click="realName">
						<image src="../../static/sz2.jpg" mode=""></image>
						<p>实名认证</p>
					</view>
					<view class="address_management" @click="addressManagement">
						<image src="../../static/sz3.jpg" mode=""></image>
						<p>地址管理</p>
					</view>
				</view>
			</view>
		</view>
		<view class="but">
			<button @click="signOut">退出登录</button>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return{
					userInfo:'',
			}
		},
		onLoad() {
			var that = this;
			var userInfo = uni.getStorageSync('userInfo');
			
			uni.request({
					url: this.host+'/api/user/checkLogin', 
					data: {
							uid:userInfo.id,
					},
					method:"post",
					success: (res) => {
							if(res.data.code == 1001){
								that.userInfo = res.data.data;
							}else{
								uni.showToast({
									title: res.data.msg,
									icon:'none',
									duration: 3000
								});
								if(res.data.code == 1003){
									setTimeout(function () {
										uni.redirectTo({
											url: '/pages/sign_in/sign_in',
										})
									}, 3000);
								}
							}
				 
					}
			});
		},
		methods:{
			// 个人中心的我的订单页面
			myOrder(){
				uni.navigateTo({
					url:"./order/my_order/my_order"
				})
			},
			// 个人中心的续租订单页面
			renewalOrder(){
				uni.navigateTo({
					url:"./order/renewal_order/renewal_order"
				})
			},
			// 个人中心的我的账户页面
			myAccount(){
				uni.navigateTo({
					url:"./assets/my_account/my_account"
				})
			},
			// 个人中心的我的账单页面
			myBill(){
				uni.navigateTo({
					url:"./assets/my_bill/my_bill"
				})
			},
			// 个人中心的我的设备页面
			myDevice(){
				uni.navigateTo({
					url:"./assets/my_device/my_device"
				})
			},
			// 个人中心的免押金额度页面
			depositFree(){
				uni.navigateTo({
					url:"./assets/deposit_free/deposit_free"
				})
			},
			// 个人中心的我的优惠券页面
			myCoupons(){
				uni.navigateTo({
					url:"./assets/my_coupons/my_coupons"
				})
			},
			// 个人中心的发票信息页面
			myInvoice(){
				uni.navigateTo({
					url:"./service/invoice/invoice"
				})
			},
			// 个人中心的预约维修页面
			repair(){
				uni.navigateTo({
					url:"./service/repair/repair"
				})
			},
			// 个人中心的账户安全页面
			account(){
				uni.navigateTo({
					url:"./set/account/account"
				})
			},
			// 个人中心的实名认证页面
			realName(){
				uni.navigateTo({
					url:"./set/real_name/real_name"
				})
			},
			// 个人中心的地址管理页面
			addressManagement(){
				uni.navigateTo({
					url:"./set/address/address_management"
				})
			},
			// 退出登录   跳转到登录页面
			signOut(){
				uni.removeStorageSync('userInfo');
				uni.redirectTo({
					url:"../sign_in/sign_in"
				})
			}
		}
	}
</script>


<style>
	.header{
		width: 750rpx;
		height: 230rpx;
		background-color: #ff6100;
		display: flex;
		justify-content: center;
	}
	.header_content{
		width: 690rpx;
		height: 230rpx;
		display: flex;
	}
	.portrait{
		width: 150rpx;
		height: 150rpx;
		border-radius: 50%;
		background-color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 20rpx;
	}
	.portrait image{
		width: 142rpx;
		height: 142rpx;
		border-radius: 50%;
	}
	.telephone{
		width: 250rpx;
		height: 150rpx;
		display: flex;
		justify-content: center;
		align-items: flex-start;
		flex-direction: column;
		margin-top: 20rpx;
		margin-left: 20rpx;
		color: #fff;
	}
	.telephone p{
		font-size: 34rpx;
		font-weight: 900;
	}
	.telephone text{
		font-size: 24rpx;
	}
	.set{
		width: 36rpx;
		height: 36rpx;
		position: absolute;
		right: 30rpx;
		top: 30rpx;
	}
	.set image{
		width: 36rpx;
		height: 36rpx;
	}
	.neck{
		width: 750rpx;
		height: 122rpx;
		background-color: #f5f5f5;
	}
	.neck_content{
		width: 690rpx;
		height: 132rpx;
		border-radius: 10px;
		background-color: #fff;
		position: absolute;
		right: 30rpx;
		top: 202rpx;
		display: flex;
	}
	.shield{
		width: 71rpx;
		height: 80rpx;
		margin-top: 26rpx;
		margin-left: 30rpx;
	}
	.neck_words{
		width: 285rpx;
		height: 132rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		margin-left: 32rpx;
		line-height: 46rpx;
	}
	.neck_words p{
		font-size: 30rpx;
		color: #ff6100;
		font-weight: 900;
	}
	.neck_words text{
		font-size: 24rpx;
		color: #656565;
	}
	.arrow{
		width: 22rpx;
		height: 25rpx;
		position: absolute;
		right: 30rpx;
		top: 56rpx;
	}
	.order{
		width: 750rpx;
		height: 253rpx;
		background-color: #f5f5f5;
	}
	.order_content{
		width: 690rpx;
		height: 233rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.order_content_head{
		width: 100%;
		height: 83rpx;
		display: flex;
	}
	.order_content_head p{
		font-size: 30rpx;
		font-weight: 900;
		margin-left: 30rpx;
		margin-top: 24rpx;
	}
	.order_content_head image{
		width: 30rpx;
		height: 30rpx;
		margin-left: 10rpx;
		margin-top: 26rpx;
	}
	.order_content_body{
		width: 100%;
		height: 120rpx;
		display: flex;
	}
	.my_order{
		width: 123rpx;
		height: 119rpx;
		margin-left: 23rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.my_order image{
		width: 80rpx;
		height: 80rpx;
	}
	.my_order p{
		font-size: 24rpx;
	}
	.renewal_order{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.renewal_order image{
		width: 80rpx;
		height: 80rpx;
	}
	.renewal_order p{
		font-size: 24rpx;
	}
	.assets{
		width: 750rpx;
		height: 401rpx;
		background-color: #f5f5f5;
	}
	.assets_content{
		width: 690rpx;
		height: 381rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.assets_content_head{
		width: 100%;
		height: 83rpx;
		display: flex;
	}
	.assets_content_head p{
		font-size: 30rpx;
		font-weight: 900;
		margin-left: 30rpx;
		margin-top: 24rpx;
	}
	.assets_content_head image{
		width: 30rpx;
		height: 30rpx;
		margin-left: 10rpx;
		margin-top: 26rpx;
	}
	.assets_content_body{
		display: flex;
		flex-wrap: wrap;
	}
	.my_account{
		width: 123rpx;
		height: 119rpx;
		margin-left: 23rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.my_account image{
		width: 80rpx;
		height: 80rpx;
	}
	.my_account p{
		font-size: 24rpx;
	}
	.my_bill{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.my_bill image{
		width: 80rpx;
		height: 80rpx;
	}
	.my_bill p{
		font-size: 24rpx;
	}
	.my_device{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.my_device image{
		width: 80rpx;
		height: 80rpx;
	}
	.my_device p{
		font-size: 24rpx;
	}
	.deposit_free{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.deposit_free image{
		width: 80rpx;
		height: 80rpx;
	}
	.deposit_free p{
		font-size: 24rpx;
	}
	.my_coupons{
		width: 123rpx;
		height: 119rpx;
		margin-left: 22rpx;
		margin-top: 30rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.my_coupons image{
		width: 80rpx;
		height: 80rpx;
	}
	.my_coupons p{
		font-size: 24rpx;
	}
	.service{
		width: 750rpx;
		height: 253rpx;
		background-color: #f5f5f5;
	}
	.service_content{
		width: 690rpx;
		height: 233rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.service_content_head{
		width: 100%;
		height: 83rpx;
		display: flex;
	}
	.service_content_head p{
		font-size: 30rpx;
		font-weight: 900;
		margin-left: 30rpx;
		margin-top: 24rpx;
	}
	.service_content_head image{
		width: 30rpx;
		height: 30rpx;
		margin-left: 10rpx;
		margin-top: 26rpx;
	}
	.service_content_body{
		width: 100%;
		height: 120rpx;
		display: flex;
	}
	.invoice_information{
		width: 123rpx;
		height: 119rpx;
		margin-left: 22rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.invoice_information image{
		width: 80rpx;
		height: 80rpx;
	}
	.invoice_information p{
		font-size: 24rpx;
	}
	.appointment_maintenance{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.appointment_maintenance image{
		width: 80rpx;
		height: 80rpx;
	}
	.appointment_maintenance p{
		font-size: 24rpx;
	}
	.rent_withdrawal{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.rent_withdrawal image{
		width: 80rpx;
		height: 80rpx;
	}
	.rent_withdrawal p{
		font-size: 24rpx;
	}
	.exchange_service{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.exchange_service image{
		width: 80rpx;
		height: 80rpx;
	}
	.exchange_service p{
		font-size: 24rpx;
	}
	.set_up{
		width: 750rpx;
		height: 273rpx;
		background-color: #f5f5f5;
	}
	.set_up_content{
		width: 690rpx;
		height: 233rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.set_up_content_head{
		width: 100%;
		height: 83rpx;
		display: flex;
	}
	.set_up_content_head p{
		font-size: 30rpx;
		font-weight: 900;
		margin-left: 30rpx;
		margin-top: 24rpx;
	}
	.set_up_content_head image{
		width: 30rpx;
		height: 30rpx;
		margin-left: 10rpx;
		margin-top: 26rpx;
	}
	.set_up_content_body{
		width: 100%;
		height: 120rpx;
		display: flex;
	}
	.account_security{
		width: 123rpx;
		height: 119rpx;
		margin-left: 22rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.account_security image{
		width: 80rpx;
		height: 80rpx;
	}
	.account_security p{
		font-size: 24rpx;
	}
	.real_name{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.real_name image{
		width: 80rpx;
		height: 80rpx;
	}
	.real_name p{
		font-size: 24rpx;
	}
	.address_management{
		width: 123rpx;
		height: 119rpx;
		margin-left: 56rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.address_management image{
		width: 80rpx;
		height: 80rpx;
	}
	.address_management p{
		font-size: 24rpx;
	}
	.but{
		width: 750rpx;
		height: 168rpx;
		background-color: #f5f5f5;
	}
	.but button{
		width: 690rpx;
		height: 88rpx;
		border-radius: 20px;
		margin: 0 auto;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #ff6100;
		color: #fff;
		font-size: 26rpx;
		font-weight: 900;
	}
</style>