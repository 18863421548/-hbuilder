<template>
	<view class="whole">
		<view class="invoice_type">
			<view class="invoice_type_content">
				<picker @change="bindPickerChange" :range="array">
					<label class="type">发票类型</label>
					<label :class="index==0?'ordinary':'increment'">{{array[index]}}</label>
				</picker>
				<image src="../../../../static/向右箭头.png" mode=""></image>
			</view>
		</view>
		<!-- 普通电子发票 -->
		<view class="ordinary_electronic_invoice" v-show="index==0">
			<view class="xian"></view>
			<view class="invoiced_amount">
				<p>开票金额</p>
				<input type="text" placeholder="本次最多位为0.00">
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
				<input type="text" placeholder="请输入发票抬头">
			</view>
			<view class="taxpayer">
				<p>纳税人识别号</p>
				<input type="text" placeholder="请输入纳税人识别号">
			</view>
			<view class="phone_number">
				<p>收票人手机号</p>
				<input type="text" placeholder="请输入收票人手机号">
			</view>
			<view class="e_mail">
				<p>收票电子邮箱</p>
				<input type="text" placeholder="请输入收票电子邮箱">
			</view>
			<view class="tips">
				<p>温馨提示:</p>
				<view class="tips_content">
					<text>1.申请增值税普通纸质发票需支付快递费。</text>
					<text>2.申请增值税专用发票金额小于200元需支付快递费。</text>
					<text class="three">3.2019年4月1日起，原适用16%的税率调整至13%</text>
				</view>
			</view>
			<button class="but">提 交</button>
			<view class="minimum"></view>
		</view>
		<!-- 增值税专用发票 -->
		<view class="value_added_tax" v-show="index==1">
			<view class="xian"></view>
			<view class="invoiced_amount">
				<p>开票金额</p>
				<input type="text" placeholder="本次最多位为0.00">
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
				<input type="text" placeholder="请输入发票抬头">
			</view>
			<view class="taxpayer">
				<p>纳税人识别号</p>
				<input type="text" placeholder="请输入纳税人识别号">
			</view>
			<view class="register_address">
				<p>工商注册地址</p>
				<input type="text" placeholder="请输入工商注册地址">
			</view>
			<view class="register_telephone">
				<p>工商注册电话</p>
				<input type="text" placeholder="手机号/固话均可，固话须带区号">
			</view>
			<view class="bank_of_deposit">
				<p>开户行</p>
				<input type="text" placeholder="请输入开户行">
			</view>
			<view class="bank_account">
				<p>银行账户</p>
				<input type="text" placeholder="请输入银行账户">
			</view>
			<view class="invoice_remarks">
				<p>打印在发票备注框中的文字</p>
				<input type="text" placeholder="此备注内容将在发票上展示">
			</view>
			<view class="customer_business_needs">
				<p>客户业务需求</p>
				<input type="text" placeholder="请输入其他要求">
			</view>
			<view class="mail_address">
				<p>邮寄地址</p>
				<input type="text" placeholder="收货人信息">
				<image src="../../../../static/向右箭头.png" mode=""></image>
			</view>
			<view class="tips">
				<p>温馨提示:</p>
				<view class="tips_content">
					<text>1.申请增值税普通纸质发票需支付快递费。</text>
					<text>2.申请增值税专用发票金额小于200元需支付快递费。</text>
					<text class="three">3.2019年4月1日起，原适用16%的税率调整至13%</text>
				</view>
			</view>
			<button class="butt">提 交</button>
			<view class="minimum"></view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				array:['普通电子发票','增值税专用发票'],
				index:0
			}
		},
		methods:{
			bindPickerChange: function(e) {		//改变的事件名
				//console.log('picker发送选择改变，携带值为', e.target.value)   用于输出改变索引值
				this.index = e.target.value			//将数组改变索引赋给定义的index变量
				this.jg=this.array[this.index]		//将array【改变索引】的值赋给定义的jg变量
			//	console.log("籍贯为：",this.jg)		//输出获取的籍贯值，例如：中国
			},
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		/* height: 1546rpx; */
		background-color: #f5f5f5;
	}
	.invoice_type{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-top: 1px solid #cccccc;
	}
	.invoice_type_content{
		width: 690rpx;
		height: 89rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.type{
		font-size: 26rpx;
	}
	.ordinary{
		margin-left: 50rpx;
		font-size: 26rpx;
	}
	.increment{
		margin-left: 50rpx;
		font-size: 26rpx;
	}
	.invoice_type image{
		margin-top: 2rpx;
		margin-left: 100rpx;
		width: 22rpx;
		height: 22rpx;
	}
	
	/* 普通电子发票 */
	.ordinary_electronic_invoice{
		
	}
	.xian{
		width: 750rpx;
		height: 20rpx;
		background-color: #f5f5f5;
	}
	/* 开票金额 */
	.invoiced_amount{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoiced_amount p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoiced_amount input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 发票内容 */
	.invoice_content{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
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
		background-color: #fff;
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
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoice_rise p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_rise input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 纳税人识别号 */
	.taxpayer{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.taxpayer p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.taxpayer input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 收票人手机号 */
	.phone_number{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.phone_number p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.phone_number input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 收票电子邮箱 */
	.e_mail{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		display: flex;
		align-items: center;
	}
	.e_mail p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.e_mail input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 温馨提示 */
	.tips{
		width: 690rpx;
		height: 200rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.tips p{
		margin-top: 40rpx;
		font-size: 20rpx;
	}
	.tips_content{
		display: flex;
		flex-direction: column;
		margin-top: 18rpx;
	}
	.tips_content text{
		font-size: 20rpx;
		margin-top: 4rpx;
	}
	.three{
		color: #e81717;
	}
	.but{
		width: 690rpx;
		height: 78rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 28rpx;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 180rpx;
	}
	/* 增值税专用发票 */
	.value_added_tax{
		
	}
	/* 工商注册地址 */
	.register_address{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.register_address p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.register_address input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 工商注册电话 */
	.register_telephone{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.register_telephone p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.register_telephone input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 开户行 */
	.bank_of_deposit{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.bank_of_deposit p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.bank_of_deposit input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 银行账户 */
	.bank_account{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.bank_account p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.bank_account input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 打印在发票备注框中的文字 */
	.invoice_remarks{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.invoice_remarks p{
		width: 186rpx;
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.invoice_remarks input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 客户业务需求 */
	.customer_business_needs{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.customer_business_needs p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.customer_business_needs input{
		font-size: 26rpx;
		margin-left: 50rpx;
		color: #999999;
	}
	/* 邮寄地址 */
	.mail_address{
		width: 750rpx;
		height: 89rpx;
		background-color: #fff;
		display: flex;
		align-items: center;
	}
	.mail_address p{
		font-size: 26rpx;
		margin-left: 30rpx;
	}
	.mail_address input{
		font-size: 26rpx;
		margin-left: 102rpx;
		color: #999999;
	}
	.mail_address image{
		margin-top: 2rpx;
		margin-left: 164rpx;
		width: 22rpx;
		height: 22rpx;
	}
	.butt{
		width: 690rpx;
		height: 78rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 28rpx;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		margin-top: 100rpx;
	}
	.minimum{
		width: 750rpx;
		height: 30rpx;
		background-color: #f5f5f5;
	}
</style>