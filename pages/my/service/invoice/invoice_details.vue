<template>
	<view>
		<view class="invoice_type">
			<p>发票类型</p>
			<text>增值税专用发票</text>
		</view>
		<view class="xian"></view>
		<view class="invoice_money">
			<p>发票金额</p>
			<text>13907.50</text>
		</view>
		<view class="invoice_content">
			<p>发票内容</p>
			<text>租赁服务费</text>
		</view>
		<view class="xian"></view>
		<view class="rise_type">
			<p>抬头类型</p>
			<text>企业</text>
		</view>
		<view class="invoice_rise">
			<p>发票抬头</p>
			<text>畅移（上海）信息科技有限公司</text>
		</view>
		<view class="taxpayer">
			<p>纳税人识别编号</p>
			<text>91310104090061156G</text>
		</view>
		<view class="register_address">
			<p>工商注册地址</p>
			<text>上海市徐汇区宜山路900号2幢16层</text>
		</view>
		<view class="register_telephone">
			<p>工商注册电话</p>
			<text>021-60544074</text>
		</view>
		<view class="bank_of_deposit">
			<p>开户行</p>
			<text>上海农村商业银行股份有限公司金桥支行</text>
		</view>
		<view class="bank_account">
			<p>银行账户</p>
			<text>50131000335320766</text>
		</view>
		<view class="invoice_remarks">
			<p>打印在发票备注框中的文字</p>
			<text>无</text>
		</view>
		<view class="customer_business_needs">
			<p>客户业务需求</p>
			<text>无</text>
		</view>
		<view class="xian"></view>
		<view class="addressee">
			<p>收件人</p>
			<text>王萌萌</text>
		</view>
		<view class="phone_number">
			<p>手机号</p>
			<text>17756118303</text>
		</view>
		<view class="receiving_address">
			<p>收件地址</p>
			<text>上海市徐汇区科技产业化大楼c栋16楼</text>
		</view>
		<view class="xian"></view>
	</view>
</template>

<script>
</script>

<style>
	/* 发票类型 */
	.invoice_type{
		width: 750rpx;
		height: 89rpx;
		border-top: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoice_type p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_type text{
		font-size: 26rpx;
		margin-left: 50rpx;
	}
	.xian{
		width: 750rpx;
		height: 20rpx;
		background-color: #f5f5f5;
	}
	/* 发票金额 */
	.invoice_money{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoice_money p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_money text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 发票内容 */
	.invoice_content{
		width: 750rpx;
		height: 89rpx;
		display: flex;
		align-items: center;
	}
	.invoice_content p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_content text{
		font-size: 26rpx;
		margin-left: 50rpx;
	}
	/* 抬头类型 */
	.rise_type{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.rise_type p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.rise_type text{
		font-size: 26rpx;
		margin-left: 50rpx;
	}
	/* 发票抬头 */
	.invoice_rise{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoice_rise p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_rise text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 纳税人识别编号 */
	.taxpayer{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.taxpayer p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.taxpayer text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 工商注册地址 */
	.register_address{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.register_address p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.register_address text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 工商注册电话 */
	.register_telephone{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.register_telephone p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.register_telephone text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 开户行 */
	.bank_of_deposit{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.bank_of_deposit p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.bank_of_deposit text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 银行账户 */
	.bank_account{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.bank_account p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.bank_account text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 打印在发票备注框中的文字 */
	.invoice_remarks{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoice_remarks p{
		width: 186rpx;
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_remarks text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 客户业务需求 */
	.customer_business_needs{
		width: 750rpx;
		height: 89rpx;
		display: flex;
		align-items: center;
	}
	.customer_business_needs p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.customer_business_needs text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 收件人 */
	.addressee{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.addressee p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.addressee text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 手机号 */
	.phone_number{
		width: 750rpx;
		height: 89rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.phone_number p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.phone_number text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 收件地址 */
	.receiving_address{
		width: 750rpx;
		height: 89rpx;
		display: flex;
		align-items: center;
	}
	.receiving_address p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.receiving_address text{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
</style>