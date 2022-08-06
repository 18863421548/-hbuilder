<template>
	<view class="whole">
		<view class="head">
			<view class="order_no">
				<p>订单编号</p>
				<text>2022061410254891002</text>
			</view>
			<view class="order_time">
				<p>下单时间</p>
				<text>2022-06-14 <span>10:15:33</span></text>
			</view>
		</view>

		<view class="all_order_second">
			<view class="heads">
				<p>订单号</p>
				<text>2011061410254891002</text>
				<span>待配送</span>
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
		</view>

		<view class="bodys">
			<view class="order_amount">
				<p>订单总额</p>
				<text>¥21200</text>
			</view>
			<view class="payment_method">
				<p>支付方式</p>
				<text>在线支付</text>
			</view>
			<view class="receiving_address">
				<p>收货地址</p>
				<text>花园庄小区</text>
			</view>
			<view class="consignee">
				<p>收货人</p>
				<text>李木子</text>
			</view>
			<view class="contact_number">
				<p>联系电话</p>
				<text>17526408365</text>
			</view>
			<view class="remarks">
				<p>备注信息</p>
				<text></text>
			</view>
		</view>

		<view class="money">
			<view class="royalties_payable">
				<p>应付使用费</p>
				<text>¥928</text>
			</view>
			<view class="margin_payable">
				<p>应付保证金</p>
				<text>¥21200</text>
			</view>
			<view class="sales_amount_payable">
				<p>应付销售金额</p>
				<text>¥0</text>
			</view>
			<view class="no_margin_deduction">
				<p>免保证金抵扣</p>
				<text>-¥0</text>
			</view>
			<view class="value_added_guarantee_amount">
				<p>增值保障金额</p>
				<text>¥0</text>
			</view>
			<view class="freight">
				<p>运费</p>
				<text>¥0</text>
			</view>
			<view class="balance_deduction">
				<p>余额抵扣</p>
				<text>-¥0</text>
			</view>
			<view class="total_amount">
				<p>合计总额</p>
				<text>¥21200</text>
			</view>
		</view>
		<button class="but">设备回收</button>
	</view>
</template>

<script>
</script>

<style>
	.whole{
		width: 100%;
		height: 1940rpx;
		background-color: #f5f5f5;
		overflow: hidden;
	}
	.head{
		width: 750rpx;
		height: 176rpx;
		background-color: #fff;
		border-top: 1px solid #cccccc;
	}
	.order_no{
		width: 690rpx;
		height: 88rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.order_no p{
		font-size: 26rpx;
		color: #999999;
	}
	.order_no text{
		font-size: 26rpx;
		margin-left: 40rpx;
	}
	.order_time{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.order_time p{
		font-size: 26rpx;
		color: #999999;
	}
	.order_time text{
		font-size: 26rpx;
		margin-left: 40rpx;
	}
	.order_time span{
		margin-left: 20rpx;
	}
	
	.all_order_second{
		width: 690rpx;
		height: 324rpx;
		border-radius: 10px;
		background-color: #fff;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.heads{
		width: 690rpx;
		height: 66rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
		font-size: 26rpx;
	}
	.heads p{
		margin-left: 20rpx;
	}
	.heads text{
		margin-left: 9rpx;
	}
	.heads span{
		margin-left: 190rpx;
		color: #ff6100;
	}
	.body{
		width: 690rpx;
		height: 257rpx;
		/* border-bottom: 1px solid #cccccc; */
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
	}
	.body_right_price p{
		font-size: 26rpx;
		color: #e81717;
		font-weight: 900;
	}
	
	.bodys{
		width: 750rpx;
		height: 520rpx;
		background-color: #fff;
		margin-top: 20rpx;
	}
	.order_amount{
		width: 690rpx;
		height: 87rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.order_amount p{
		font-size: 26rpx;
		color: #999999;
	}
	.order_amount text{
		font-size: 26rpx;
		margin-left: 43rpx;
	}
	
	.payment_method{
		width: 690rpx;
		height: 87rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.payment_method p{
		font-size: 26rpx;
		color: #999999;
	}
	.payment_method text{
		font-size: 26rpx;
		margin-left: 43rpx;
	}
	
	.receiving_address{
		width: 690rpx;
		height: 87rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.receiving_address p{
		font-size: 26rpx;
		color: #999999;
	}
	.receiving_address text{
		font-size: 26rpx;
		margin-left: 43rpx;
	}
	
	.consignee{
		width: 690rpx;
		height: 87rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.consignee p{
		font-size: 26rpx;
		color: #999999;
	}
	.consignee text{
		font-size: 26rpx;
		margin-left: 69rpx;
	}
	
	.contact_number{
		width: 690rpx;
		height: 87rpx;
		border-bottom: 1px solid #cccccc;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.contact_number p{
		font-size: 26rpx;
		color: #999999;
	}
	.contact_number text{
		font-size: 26rpx;
		margin-left: 43rpx;
	}
	
	.remarks{
		width: 690rpx;
		height: 87rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.remarks p{
		font-size: 26rpx;
		color: #999999;
	}
	.remarks text{
		font-size: 26rpx;
		margin-left: 43rpx;
	}
	
	.money{
		width: 750rpx;
		height: 710rpx;
		background-color: #fff;
		margin-top: 24rpx;
	}
	.royalties_payable{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.royalties_payable p{
		font-size: 26rpx;
	}
	.royalties_payable text{
		font-size: 26rpx;
	}
	
	.margin_payable{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.margin_payable p{
		font-size: 26rpx;
	}
	.margin_payable text{
		font-size: 26rpx;
	}
	
	.sales_amount_payable{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.sales_amount_payable p{
		font-size: 26rpx;
	}
	.sales_amount_payable text{
		font-size: 26rpx;
	}
	
	.no_margin_deduction{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.no_margin_deduction p{
		font-size: 26rpx;
	}
	.no_margin_deduction text{
		font-size: 26rpx;
		color: #e81717;
	}
	
	.value_added_guarantee_amount{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.value_added_guarantee_amount p{
		font-size: 26rpx;
	}
	.value_added_guarantee_amount text{
		font-size: 26rpx;
	}
	
	.freight{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.freight p{
		font-size: 26rpx;
	}
	.freight text{
		font-size: 26rpx;
	}
	
	.balance_deduction{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.balance_deduction p{
		font-size: 26rpx;
	}
	.balance_deduction text{
		font-size: 26rpx;
		color: #e81717;
	}
	
	.total_amount{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		border-top: 1px solid #cccccc;
	}
	.total_amount p{
		font-size: 26rpx;
		font-weight: 900;
	}
	.total_amount text{
		font-size: 26rpx;
		font-weight: 900;
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
		margin-top: 20rpx;
		font-weight: 900;
	}
</style>