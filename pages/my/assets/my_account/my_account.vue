<template>
	<view>
		<view class="account">
			<view class="account_content">
				<view class="central">
					<view class="account_content_left">
						<text>账户余额</text>
						<p>0 <span>元</span></p>
					</view>
					<view class="account_content_right">
						<text>冻结余额</text>
						<p>0 <span>元</span></p>
					</view>
				</view>
				<button class="but">立即提现</button>
			</view>
		</view>
		<view class="xian"></view>
		<view class="nav">
			<view :class="activite==1?'bar':'index'" @click="ckeckIndex(1)">账单支付</view>
			<view :class="activite==2?'bar':'index'" @click="ckeckIndex(2)">账户退款</view>
			<view :class="activite==3?'bar':'index'" @click="ckeckIndex(3)">提现记录</view>
		</view>
		
		
		<!-- 账单支付 -->
		<view class="payment" v-show="activite==1" v-for="item in list1">
			<view class="payment_content">
				<view class="content">
					<p>{{item.order}}</p>
					<text>{{item.time}}</text>
				</view>
				<span>{{item.money}}</span>
			</view>
		</view>
		<!-- 账户退款 -->
		<view class="payment" v-show="activite==2" v-for="item in list2">
			<view class="payment_content">
				<view class="content">
					<p>{{item.order}}</p>
					<text>{{item.time}}</text>
				</view>
				<span>{{item.money}}</span>
			</view>
		</view>
		<!-- 提现记录 -->
		<view class="payment" v-show="activite==3" v-for="item in list3">
			<view class="payment_content">
				<view class="content">
					<p>{{item.order}}</p>
					<text>{{item.time}}</text>
				</view>
				<span>{{item.money}}</span>
			</view>
		</view>
		
		
		
		
	</view>
</template>

<script>
	export default {
		data(){
			return{
				activite:1,
				list1:[
					{
						order:"订单支付",
						time:"2022-06-22 10:54:53",
						money:"-1960.00"
					},
					{
						order:"订单支付",
						time:"2022-06-22 10:54:53",
						money:"-1960.00"
					},
					{
						order:"订单支付",
						time:"2022-06-22 10:54:53",
						money:"-1960.00"
					}
				],
				list2:[
					{
						order:"取消订单退款",
						time:"2022-06-22 10:54:53",
						money:"+1960.00"
					},
					{
						order:"取消订单退款",
						time:"2022-06-22 10:54:53",
						money:"+1960.00"
					},
					{
						order:"取消订单退款",
						time:"2022-06-22 10:54:53",
						money:"+1960.00"
					}
				],
				list3:[
					{
						order:"提现成功",
						time:"2022-06-22 10:54:53",
						money:"-500.00"
					},
					{
						order:"提现成功",
						time:"2022-06-22 10:54:53",
						money:"-500.00"
					},
					{
						order:"提现成功",
						time:"2022-06-22 10:54:53",
						money:"-500.00"
					}
				]
			}
		},
		methods:{
			ckeckIndex(e){
				this.activite=e
			}
		}
	}
</script>

<style>
	.account{
		width: 750rpx;
		height: 449rpx;
		background: linear-gradient(#ff6301, #fe9011);
		overflow: hidden;
	}
	.account_content{
		width: 690rpx;
		height: 374rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 40rpx;
		display: flex;
		flex-direction: column;
	}
	.central{
		display: flex;
	}
	.account_content_left{
		width: 345rpx;
		height: 150rpx;
		margin-top: 60rpx;
		border-right: 1px solid #cccccc;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.account_content_left text{
		font-size: 26rpx;
		font-weight: 900;
		color: #999999;
		margin-top: 20rpx;
	}
	.account_content_left p{
		font-size: 50rpx;
		font-weight: 900;
		margin-top: 20rpx;
	}
	.account_content_left span{
		font-size: 26rpx;
	}
	.account_content_right{
		width: 345rpx;
		height: 150rpx;
		margin-top: 60rpx;
		display: flex;
		flex-direction: column;
		flex-wrap: wrap;
		align-items: center;
	}
	.account_content_right text{
		font-size: 26rpx;
		font-weight: 900;
		color: #999999;
		margin-top: 20rpx;
	}
	.account_content_right p{
		font-size: 50rpx;
		font-weight: 900;
		margin-top: 20rpx;
	}
	.account_content_right span{
		font-size: 26rpx;
	}
	.but{
		width: 500rpx;
		height: 80rpx;
		border-radius: 40rpx;
		color: #fff;
		background-color: #fe9011;
		margin: 0 auto;
		margin-top: 38rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.xian{
		width: 750rpx;
		height: 20rpx;
		background-color: #f5f5f5;
	}
	.nav{
		width: 750rpx;
		height: 87rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		justify-content: space-around;
	}
	.bar{
		width: 120rpx;
		height: 87rpx;
		font-size: 26rpx;
		border-bottom: 2px solid #fe9011;
		color: #fe9011;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.index{
		width: 120rpx;
		height: 87rpx;
		font-size: 26rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.payment{
		width: 750rpx;
		height: 124rpx;
		border-bottom: 1px solid #cccccc;
	}
	.payment_content{
		width: 690rpx;
		height: 124rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.content{
		width: 270rpx;
		height: 74rpx;
		/* background-color: aqua; */
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.content p{
		font-size: 26rpx;
	}
	.content text{
		font-size: 24rpx;
		color: #999999;
	}
	.payment_content span{
		font-size: 24rpx;
		color: #999999;
	}
</style>