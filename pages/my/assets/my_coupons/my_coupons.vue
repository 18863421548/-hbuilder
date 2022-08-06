<template>
	<view class="whole">
		<view class="head">
			<view class="head_content">
				<view :class="activite==1?'nav':'click_nav'" @click="ckeckIndex(1)">
					未使用
				</view>
				<view :class="activite==2?'nav':'click_nav'" @click="ckeckIndex(2)">
					已使用
				</view>
				<view :class="activite==3?'nav':'click_nav'" @click="ckeckIndex(3)">
					已过期
				</view>
			</view>
		</view>
		
		<!--未使用-->
		<view class="coupon" v-show="activite==1" v-for="item in list1">
			<!-- 优惠券左侧盒子 -->
			<view class="coupon_left">
				<view class="circle">
					<!-- <uni-data-checkbox v-model="radio1" :localdata="sex"></uni-data-checkbox> -->
				</view>
				<view class="words">
					<p>{{item.title}}</p>
					<text>&nbsp;</text>
					<text>到期时间：{{item.e_date}}</text>
				</view>
				<view class="price">
					<p>{{item.cut_price}}</p>
					<text>元</text>
				</view>
			</view>
			<!-- 虚线 -->
			<view class="split-line"></view>
			<!-- 优惠券右侧盒子 -->
			<view class="coupon_right">
				<view class="coupon_right_content">
					<view class="coupon_right_content_circular">
						<p>券</p>
					</view>
				</view>
			</view>
		</view>
		<!--已使用-->
		<view class="coupon" v-show="activite==2" v-for="item in list2">
			<!-- 优惠券左侧盒子 -->
			<view class="coupon_left">
				<view class="circle">
					<!-- <uni-data-checkbox v-model="radio1" :localdata="sex"></uni-data-checkbox> -->
				</view>
				<view class="words">
					<p>{{item.title}}</p>
					<text>&nbsp;</text>
					<text>到期时间：{{item.e_date}}</text>
				</view>
				<view class="price">
					<p>{{item.cut_price}}</p>
					<text>元</text>
				</view>
			</view>
			<!-- 虚线 -->
			<view class="split-line"></view>
			<!-- 优惠券右侧盒子 -->
			<view class="coupon_right">
				<view class="coupon_right_content">
					<view class="coupon_right_content_circular">
						<p>券</p>
					</view>
				</view>
			</view>
		</view>
		<!--已过期-->
		<view class="coupon" v-show="activite==3" v-for="item in list3">
			<!-- 优惠券左侧盒子 -->
			<view class="coupon_left">
				<view class="circle">
					<!-- <uni-data-checkbox v-model="radio1" :localdata="sex"></uni-data-checkbox> -->
				</view>
				<view class="words">
					<p>{{item.title}}</p>
					<text>&nbsp;</text>
					<text>到期时间：{{item.e_date}}</text>
				</view>
				<view class="price">
					<p>{{item.cut_price}}</p>
					<text>元</text>
				</view>
			</view>
			<!-- 虚线 -->
			<view class="split-line"></view>
			<!-- 优惠券右侧盒子 -->
			<view class="coupon_right">
				<view class="coupon_right_content">
					<view class="coupon_right_content_circular">
						<p>券</p>
					</view>
				</view>
			</view>
		</view>
		
		
		
		
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				activite: 1,
				radio1: 0,
				sex: [{
					text: '',
					value: 1
				},],
				list1:[],
				list2:[],
				list3:[],
				page1:1,
				page2:1,
				page3:1,
			}
		},
		onLoad() {
			this.coupons();
		},
		onReachBottom(){
			this.coupons();
		},
		methods: {
			ckeckIndex(e) {
				this.activite = e;
				this.coupons();
			},
			coupons(){
				var that = this;
				var userInfo = uni.getStorageSync('userInfo');
				var pages = that.page1;
				switch(that.activite){
					case 1:
						pages = that.page1;
						break;
					case 2:
						pages = that.page2;
						break;
					case 3:
						pages = that.page3;
						break;
				}
				uni.request({
						url: this.host+'/api/user/coupons', 
						data: {
								uid:userInfo.id,
								index:that.activite,
								page:pages,

						},
						method:"post",
						success: (res) => {
								if(res.data.code == 1001){
									switch(that.activite){
										case 1:
									
											that.list1 = [...that.list1,...res.data.data];
											that.page1 = res.data.pages;
											break;
										case 2:
											console.log(res.data.data);	
											that.list2 = [...that.list2,...res.data.data];
											that.page2 = res.data.pages;
											break;
										case 3:
											that.list3 = [...that.list3,...res.data.data];
											that.page3 = res.data.pages;
											break;
									}
									
									
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
			}
		}
	}
</script>

<style>
	.whole {
		width: 100%;
		height: 1246rpx;
		background-color: #f5f5f5;
	}
	.head {
		width: 750rpx;
		height: 90rpx;
		background-color: #fff;
		border-top: 1px solid #cccccc;
	}

	.head_content {
		width: 690rpx;
		height: 90rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-around;
	}
	.nav {
		width: 86rpx;
		height: 86rpx;
		font-size: 26rpx;
		color: #ff6100;
		border-bottom: 2px solid #ff6100;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.click_nav {
		width: 86rpx;
		height: 86rpx;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	
	
	
	/* 优惠券 */
	.coupon {
		width: 690rpx;
		height: 150rpx;
		border-radius: 10px;
		background-color: #f4e4e4;
		margin: 0 auto;
		margin-top: 40rpx;
		display: flex;
	}
	/* 优惠卷左侧盒子 */
	.coupon_left{
		width: 532rpx;
		height: 150rpx;
		display: flex;
		/* align-items: center; */
	}
	/* 虚线 */
	.split-line {
	  position: relative;
	  flex: 0 0 0;
	  margin: 0 10rpx 0 6rpx;
	  border-left: 2rpx dashed #fff;
	}
	/*给虚线加两个伪类，基本样式如下*/
	.split-line:before,
	.split-line:after {
	  content: '';
	  position: absolute;
	  width: 32rpx;
	  height: 16rpx;
	  background: #f5f5f5;
	  left: -18rpx;
	  z-index: 1;
	}
	/*几个伪类化成的圆弧的样式以及位置（置于顶部）我把它放在一起了*/
	.coupon_left:before,
	.coupon_right:before,
	.split-line:before {
	  border-radius: 0 0 16rpx 16rpx;
	  top: 0;
	}
	/*几个伪类化成的圆弧的样式以及位置（置于底部）我把它放在一起了*/
	.coupon_left:after,
	.coupon_right:after,
	.split-line:after {
	  border-radius: 16rpx 16rpx 0 0;
	  bottom: 0;
	}
	/* 优惠卷右侧盒子 */
	.coupon_right{
		width: 158rpx;
		height: 150rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
	
	.circle{
		width: 20rpx;
		height: 20rpx;
		margin-left: 10rpx;
		margin-top: 32rpx;
		border-radius: 50%;
		border: 1px solid #cccccc
	}
	.words{
		width: 378rpx;
		height: 98rpx;
		/* background-color: aqua; */
		margin-top: 26rpx;
		margin-left: 10rpx;
		display: flex;
		flex-direction: column;
		/* justify-content: center; */
	}
	.words p{
		height: 44rpx;
		font-size: 30rpx;
		font-weight: 800;
	}
	.words text{
		font-size: 20rpx;
	}
	.price{
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.price p{
		font-size: 50rpx;
		font-weight: 900;
		color: #e81717;
	}
	.price text{
		font-size: 24rpx;
		color: #e81717;
		margin-top: 14rpx;
		margin-left: 6rpx;
	}
	
	.coupon_right_content{
		width: 90rpx;
		height: 90rpx;
		border-radius: 50%;
		border: 1px solid #e81717;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.coupon_right_content_circular{
		width: 78rpx;
		height: 78rpx;
		border-radius: 50%;
		border: 1px solid #e81717;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.coupon_right_content_circular p{
		font-size: 50rpx;
		color: #e81717;
	}
</style>
