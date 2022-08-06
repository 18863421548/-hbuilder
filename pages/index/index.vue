<template>
	<view class="whole">
		<view class="head">
			<input type="text" placeholder="请输入搜索内容" class="input">
			<image src="../../static/fdj.jpg" mode=""></image>
		</view>
		<!-- 轮播图 -->
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval"
				:duration="duration">
				<swiper-item v-for="(item,index) in banner">
					<image :src="item.pic" mode=""></image>
				</swiper-item>
	
			</swiper>
		</view>
		<!-- 导航 -->
		<view class="navigation">
			<view class="order" @click="myOrder">
				<image src="../../static/nav1.jpg" mode=""></image>
				<p>我的订单</p>
			</view>
			<view class="account">
				<image src="../../static/nav2.jpg" mode=""></image>
				<p>我的账户</p>
			</view>
			<view class="bill">
				<image src="../../static/nav3.jpg" mode=""></image>
				<p>我的账单</p>
			</view>
			<view class="coupon">
				<image src="../../static/nav4.jpg" mode=""></image>
				<p>优惠券</p>
			</view>
		</view>
		<!-- 申请步骤 -->
		<view class="application_steps">
			<view class="application_steps_head">
				<p>申请步骤</p>
				<image src="../../static/圆圈.jpg" mode=""></image>
			</view>
			<view class="application_steps_body">
				<view class="checkout">
					<image src="../../static/sq1.jpg" mode=""></image>
					<p>下单成功</p>
				</view>
				<view class="jian">
					<image src="../../static/jjj.jpg" mode=""></image>
				</view>
				<view class="risk_audit">
					<image src="../../static/sq2.jpg" mode=""></image>
					<p>风控审核</p>
				</view>
				<view class="jian">
					<image src="../../static/jjj.jpg" mode=""></image>
				</view>
				<view class="sign_contract">
					<image src="../../static/sq3.jpg" mode=""></image>
					<p>签署合同</p>
				</view>
			</view>
		</view>
		<!-- 限量特惠 -->
		<view class="limit_preferential">
			<view class="limit_preferential_head" @click="limitedSpecial">
				<p>限量特惠</p>
				<image src="../../static/圆圈.jpg" mode=""></image>
			</view>
			
			
			
			
			<view class="limit_preferential_body" >
				<view class="preferential_computer" v-for="(item,index) in xxx_list">
					<p>{{item.title}}</p>
					<text>{{item.subtitle}}</text>
					<image :src="item.pic" mode=""></image>
				</view>
				

			</view>
		</view>
		<!-- 行政办公 -->
		<view class="administrative_office">
			<view class="administrative_office_within">
				<view class="administrative_office_left">
					<p>行政办公</p>
					<image src="../../static/yy1.jpg" mode=""></image>
				</view>
				<view class="administrative_office_right">
					<p>查看更多</p>
				</view>
			</view>
		</view>
		
		
		<view class="computer_list">
			<view class="computer" v-for="item in xz_list">
				<image :src="item.pic" mode=""></image>
				<p>{{item.title}}</p>
				<text>{{item.subtitle}}</text>
				<span>{{item.lease_fee}}</span>
			</view>
		</view>
		
		<!-- 技术开发 -->
		<view class="technological_development">
			<view class="technological_development_within">
				<view class="technological_development_left">
					<p>技术开发</p>
					<image src="../../static/yy2.jpg" mode=""></image>
				</view>
				<view class="technological_development_right">
					<p>查看更多</p>
				</view>
			</view>
		</view>
		
		<view class="computer_list">
			<view class="computer" v-for="item in js_list">
				<image :src="item.pic" mode=""></image>
				<p>{{item.title}}</p>
				<text>{{item.subtitle}}</text>
				<span>{{item.lease_fee}}</span>
			</view>
		</view>
		
		<!-- 商务便捷 -->
		<view class="convenient_business">
			<view class="convenient_business_within">
				<view class="convenient_business_left">
					<p>商务便捷</p>
					<image src="../../static/yy3.jpg" mode=""></image>
				</view>
				<view class="convenient_business_right">
					<p>查看更多</p>
				</view>
			</view>
		</view>
		
		<view class="computer_list">
			<view class="computer" v-for="item in sw_list">
				<image :src="item.pic" mode=""></image>
				<p>{{item.title}}</p>
				<text>{{item.subtitle}}</text>
				<span>{{item.lease_fee}}</span>
			</view>
		</view>
		
		<!-- 图形处理 -->
		<view class="graphic_processing">
			<view class="graphic_processing_within">
				<view class="graphic_processing_left">
					<p>图形处理</p>
					<image src="../../static/yy4.jpg" mode=""></image>
				</view>
				<view class="graphic_processing_right">
					<p>查看更多</p>
				</view>
			</view>
		</view>
		
		<view class="computer_list">
			<view class="computer" v-for="item in tx_list">
				<image :src="item.pic" mode=""></image>
				<p>{{item.title}}</p>
				<text>{{item.subtitle}}</text>
				<span>{{item.lease_fee}}</span>
			</view>
		</view>
		
		<!-- 外设配件 -->
		<view class="peripheral_accessories">
			<view class="peripheral_accessories_within">
				<view class="peripheral_accessories_left">
					<p>外设配件</p>
					<image src="../../static/yy5.jpg" mode=""></image>
				</view>
				<view class="peripheral_accessories_right">
					<p>查看更多</p>
				</view>
			</view>
		</view>
		
		<view class="computer_list">
			<view class="computer" v-for="item in pj_list">
				<image :src="item.pic" mode=""></image>
				<p>{{item.title}}</p>
				<text>{{item.subtitle}}</text>
				<span>{{item.lease_fee}}</span>
			</view>
		</view>
		<view class="bottom">
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				banner:[],
				xxx_list:[],//限量优惠
				xz_list:[],//行政办公
				js_list:[],//技术开发
				sw_list:[],//商务便捷
				tx_list:[],//图形处理
				pj_list:[],//外设配件
				list:[
					{
						path:"../../static/62d1936d53fef.png",
						name:"Think Pad X13",
						to_configure:"i5-10|8G|25G|核显|13.3",
						price:"￥299/月"
					},
					{
						path:"../../static/62d1936d53fef.png",
						name:"Think Pad X13",
						to_configure:"i5-10|8G|25G|核显|13.3",
						price:"￥299/月"
					},
					{
						path:"../../static/62d1936d53fef.png",
						name:"Think Pad X13",
						to_configure:"i5-10|8G|25G|核显|13.3",
						price:"￥299/月"
					},
					{
						path:"../../static/62d1936d53fef.png",
						name:"Think Pad X13",
						to_configure:"i5-10|8G|25G|核显|13.3",
						price:"￥299/月"
					},
				],
				
			}
		},
		onLoad(){
			var that = this;			
			uni.request({
					url: this.host+'/api/index/index', 
					data: {},
					method:"post",
					success: (res) => {
						if(res.data.code == 1001){

							that.banner = res.data.data.banner;
							that.xxx_list = res.data.data.xxx_list;
							that.xz_list = res.data.data.xz_list;
							that.js_list = res.data.data.js_list;
							that.sw_list = res.data.data.sw_list;
							that.tx_list = res.data.data.tx_list;
							that.pj_list = res.data.data.pj_list;
						}else{
							uni.showToast({
								title: res.data.msg,
								icon:'none',
								duration: 3000
							});
						}
					}
			});
		},
		methods: {
			// 首页的我的订单页面
			myOrder(){
				uni.navigateTo({
					url:"../my/order/my_order/my_order"
				})
			},
			// 限量特惠
			limitedSpecial(){
				uni.navigateTo({
					url:"./limited_special"
				})
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		/* height: 2500rpx; */
		background-color: #f5f5f5;
		z-index: 1;
	}
	.head {
		overflow: hidden;
		position: relative;
		height: 160px;
	}
	.head::after {
		content: '';
		width: 120%;
		height: 100%;
		position: absolute;
		left: -10%;
		top: 0;
		z-index: -1;
		border-radius: 0 0 50% 50%;
		background: #ff6100;
		z-index: 2;
	}
	.input {
		position: absolute;
		width: 626rpx;
		height: 70rpx;
		margin: 0 auto;
		background-color: #fff;
		border-radius: 20px;
		margin-top: 10rpx;
		margin-left: 30rpx;
		font-size: 24rpx;
		padding-left: 64rpx;
		z-index: 3;
	}
	.head image{
		position: absolute;
		width: 26rpx;
		height: 26rpx;
		z-index: 4;
		top: 32rpx;
		left: 50rpx;
	}
	/* 轮播图 */
	.uni-margin-wrap {
		width: 690rpx;
		height: 340rpx;
		margin: 0 auto;
		background-color: rgba(0, 0, 0, 0);
		position: absolute;
		z-index: 4;
		top: 110rpx;
		left: 30rpx;
	}
	.swiper swiper-item{
		background-color: rgba(0, 0, 0, 0);
	}
	.swiper image{
		width: 100%;
		height: 300rpx;
		border-radius: 10px;
	}
	.navigation{
		width: 690rpx;
		height: 182rpx;
		margin: 0 auto;
		margin-top: 114rpx;
		background-color: #fff;
		border-radius: 10px;
		display: flex;
		align-items: center;
	}
	.order{
		width: 104rpx;
		height: 121rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		margin-left: 20rpx;
	}
	.order image{
		width: 80rpx;
		height: 80rpx;
	}
	.order p{
		font-size: 26rpx;
	}
	.account{
		width: 104rpx;
		height: 121rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		margin-left: 79rpx;
	}
	.account image{
		width: 80rpx;
		height: 80rpx;
	}
	.account p{
		font-size: 26rpx;
	}
	.bill{
		width: 104rpx;
		height: 121rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		margin-left: 80rpx;
	}
	.bill image{
		width: 80rpx;
		height: 80rpx;
	}
	.bill p{
		font-size: 26rpx;
	}
	.coupon{
		width: 104rpx;
		height: 121rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		margin-left: 79rpx;
	}
	.coupon image{
		width: 80rpx;
		height: 80rpx;
	}
	.coupon p{
		font-size: 26rpx;
	}
	.application_steps{
		width: 690rpx;
		height: 250rpx;
		background-color: #fff;
		margin: 0 auto;
		border-radius: 10px;
		margin-top: 20rpx;
	}
	.application_steps_head{
		width: 100%;
		height: 89rpx;
		display: flex;
	}
	.application_steps_head p{
		font-size: 30rpx;
		font-weight: 900;
		margin-top: 24rpx;
		margin-left: 21rpx;
	}
	.application_steps_head image{
		margin-top: 34rpx;
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.application_steps_body{
		width: 100%;
		height: 136rpx;
		display: flex;
	}
	.checkout{
		width: 103rpx;
		height: 136rpx;
		margin-left: 30rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.checkout image{
		width: 69rpx;
		height: 77rpx;
	}
	.checkout p{
		font-size: 25rpx;
	}
	.jian{
		width: 156rpx;
		height: 136rpx;
	}
	.jian image{
		width: 156rpx;
		height: 136rpx;
	}
	.risk_audit{
		width: 103rpx;
		height: 136rpx;
		margin-left: 5rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.risk_audit image{
		width: 69rpx;
		height: 77rpx;
	}
	.risk_audit p{
		font-size: 25rpx;
	}
	.sign_contract{
		width: 103rpx;
		height: 136rpx;
		margin-left: 5rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}
	.sign_contract image{
		width: 69rpx;
		height: 77rpx;
	}
	.sign_contract p{
		font-size: 25rpx;
	}
	.limit_preferential{
		width: 690rpx;
		height: 290rpx;
		background-color: #fff;
		margin: 0 auto;
		border-radius: 10px;
		margin-top: 20rpx;
	}
	.limit_preferential_head{
		width: 100%;
		height: 89rpx;
		/* background-color: #ff6100; */
		display: flex;
	}
	.limit_preferential_head p{
		font-size: 30rpx;
		font-weight: 900;
		margin-top: 24rpx;
		margin-left: 21rpx;
	}
	.limit_preferential_head image{
		margin-top: 34rpx;
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.limit_preferential_body{
		width: 650rpx;
		height: 180rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.preferential_computer{
		width: 310rpx;
		height: 180rpx;
		background-color: #fff;
		border-radius: 10px;
		box-shadow: 1px 1px 2px 2px #f5f5f5;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.preferential_computer p{
		font-weight: 900;
		font-size: 24rpx;
		margin-top: 21rpx;
	}
	.preferential_computer text{
		font-size: 20rpx;
		margin-top: 6rpx;
		/* letter-spacing: 2rpx; */
	}
	.preferential_computer image{
		width: 128rpx;
		height: 85rpx;
		margin-top: 20rpx;
	}
	
	
	
	
	/* 行政办公 */
	.administrative_office{
		width: 750rpx;
		height: 79rpx;
		background-color: #fdf1e3;
		margin-top: 20rpx;
	}
	.administrative_office_within{
		width: 690rpx;
		height: 79rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.administrative_office_left{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		font-size: 30rpx;
		font-weight: 900;
	}
	.administrative_office_left image{
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.administrative_office_right{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		font-size: 20rpx;
		color: #555555;
	}
	
	
	
	
	
	.computer_list{
		width: 690rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
	}
	.computer{
		width: 335rpx;
		height: 443rpx;
		border: 1px solid #f5f5f5;
		background-color: #fff;
		border-radius: 10px;
		margin-top: 22rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.computer image{
		width: 335rpx;
		height: 242rpx;
	}
	.computer p{
		font-size: 28rpx;
		font-weight: 900;
	}
	.computer text{
		font-size: 20rpx;
		margin-top: 10rpx;
	}
	.computer span{
		font-size: 28rpx;
		color: #e81717;
		font-weight: 900;
		margin-top: 40rpx;
	}
	
	/* 技术开发 */
	.technological_development{
		width: 750rpx;
		height: 79rpx;
		background-color: #e2eefc;
		margin-top: 20rpx;
	}
	.technological_development_within{
		width: 690rpx;
		height: 79rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.technological_development_left{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		font-size: 30rpx;
		font-weight: 900;
	}
	.technological_development_left image{
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.technological_development_right{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		font-size: 20rpx;
		color: #555555;
	}
	
	/* 商务便捷 */
	.convenient_business{
		width: 750rpx;
		height: 79rpx;
		background-color: #f8e1db;
		margin-top: 20rpx;
	}
	.convenient_business_within{
		width: 690rpx;
		height: 79rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.convenient_business_left{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		font-size: 30rpx;
		font-weight: 900;
	}
	.convenient_business_left image{
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.convenient_business_right{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		font-size: 20rpx;
		color: #555555;
	}
	
	
	/* 图形处理 */
	.graphic_processing{
		width: 750rpx;
		height: 79rpx;
		background-color: #dfe6ee;
		margin-top: 20rpx;
	}
	.graphic_processing_within{
		width: 690rpx;
		height: 79rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.graphic_processing_left{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		font-size: 30rpx;
		font-weight: 900;
	}
	.graphic_processing_left image{
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.graphic_processing_right{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		font-size: 20rpx;
		color: #555555;
	}
	
	/* 外设配件 */
	
	.peripheral_accessories{
		width: 750rpx;
		height: 79rpx;
		background-color: #cde4f4;
		margin-top: 20rpx;
	}
	.peripheral_accessories_within{
		width: 690rpx;
		height: 79rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.peripheral_accessories_left{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		font-size: 30rpx;
		font-weight: 900;
	}
	.peripheral_accessories_left image{
		margin-left: 10rpx;
		width: 25rpx;
		height: 25rpx;
	}
	.peripheral_accessories_right{
		width: 345rpx;
		height: 79rpx;
		display: flex;
		align-items: center;
		justify-content: flex-end;
		font-size: 20rpx;
		color: #555555;
	}
	.bottom{
		width: 750rpx;
		height: 20rpx;
		background-color: #f5f5f5;
	}
</style>
