<template>
	<view class="whole">
		<view class="head">
			<p>为了保护您的账户安全，请先完成实名认证</p>
		</view>
		<view class="process">
			<view class="process_top">
				<image src="../../../../static/sm1.jpg" mode="" class="img1"></image>
				<view class="dotted_line"></view>
				<image src="../../../../static/sm6.jpg" mode="" class="img2"></image>
				<view class="dotted_line"></view>
				<image src="../../../../static/sm3.jpg" mode="" class="img3"></image>
			</view>
			<view class="process_bottom">
				<text class="text1">选择认证角色</text>
				<text class="text2">填写信息认证</text>
				<text class="text3">提交审核</text>
			</view>
		</view>
		<view class="certified_enterprise">
			<p>认证企业</p>
		</view>
		<view class="legal_person">
			<!-- 是否为法人代表 -->
			<view class="invoice_type">
				<view class="invoice_type_content">
					<picker @change="bindPickerChange" :range="array">
						<label class="type">是否为法人代表</label>
						<label :class="index==0?'ordinary':'increment'">{{array[index]}}</label>
					</picker>
					<image src="../../../../static/向右箭头.png" mode=""></image>
				</view>
			</view>
			<view class="name">
				<p>企业法人姓名</p>
				<input type="text" placeholder="请输入姓名">
			</view>
			<view class="id_number">
				<p>企业法人身份证号</p>
				<input type="text" placeholder="请输入证件号码">
			</view>
		</view>
		<!-- 法人身份证上传 -->
		<view class="id_card_upload">
			<view class="id_card_upload_top">
				<p>企业法人身份证上传</p>
			</view>
			<view class="id_card_upload_bottom">
				<view class="human_face" @click="humanFace">
					<image src="../../../../static/sfz1.jpg" mode=""></image>
					<p>身份证人像面</p>
				</view>
				<view class="national_emblem" @click="nationalEmblem">
					<image src="../../../../static/sfz2.jpg" mode=""></image>
					<p>身份证国徽面</p>
				</view>
			</view>
		</view>
		<!-- 企业名称等 -->
		<view class="enterprise">
			<view class="enterprise_name">
				<p>企业名称</p>
				<input type="text" placeholder="请输入企业名称">
			</view>
			<view class="unified_social_credit_code">
				<p>统一社会信用代码</p>
				<input type="text" placeholder="请输入统一社会信用代码">
			</view>
		</view>
		<!-- 营业执照上传 -->
		<view class="business_license">
			<view class="business_license_top">
				<p>营业执照上传</p>
				<text>请上传彩色原件或加盖公司公章的复印件</text>
			</view>
			<view class="business_license_bottom">
				<view class="upload_business_license" @click="uploadBusinesslicense">
					<image src="../../../../static/营业执照.jpg" mode=""></image>
					<p>营业执照上传</p>
				</view>
			</view>
		</view>
		<!-- 企业授权书上传 -->
		<view class="enterprise_power_attorney">
			<view class="enterprise_power_attorney_top">
				<p>企业授权书上传</p>
				<text>请点击<span class="download">下载企业授权书《企业授权书》</span>打印签字盖章拍照</text>
			</view>
			<view class="enterprise_power_attorney_bottom">
				<view class="upload_enterprise_power_attorney" @click="uploadBusinesslicense">
					<image src="../../../../static/营业执照.jpg" mode=""></image>
					<p>授权书上传</p>
				</view>
			</view>
		</view>
		<!-- 法人手机号 验证码 -->
		<view class="phone">
			<view class="telephone">
				<p>法人手机号码</p>
				<input type="text" placeholder="请输入法人手机号码">
			</view>
			<view class="verification_code">
				<p>短信验证码</p>
				<input type="text" placeholder="请输入验证码">
				<text>获取验证码</text>
			</view>
		</view>
		<!-- 我已阅读并同意《用户个人信息授权协议》 -->
		<view class="agreement">
			<!-- 同意按钮 -->
			<u-checkbox-group>
				<u-checkbox v-model="checked" shape="square" label=""></u-checkbox>
			</u-checkbox-group>
			<text>我已阅读并同意<span class="download">《用户个人信息授权协议》</span></text>
		</view>
		<button class="but" @click="submit">提交保存</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				array:['我是法人代表','我不是法人代表'],
				index:0,
				imgArr:[],
			}
		},
		methods:{
			bindPickerChange: function(e) {		//改变的事件名
				//console.log('picker发送选择改变，携带值为', e.target.value)   用于输出改变索引值
				this.index = e.target.value			//将数组改变索引赋给定义的index变量
				this.jg=this.array[this.index]		//将array【改变索引】的值赋给定义的jg变量
			//	console.log("籍贯为：",this.jg)		//输出获取的籍贯值，例如：中国
			},
			// 人面上传
			humanFace(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 国徽上传
			nationalEmblem(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 营业执照上传
			uploadBusinesslicense(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 提交保存
			submit(){
				uni.navigateTo({
					url:"./authentication_results"
				})
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 2400rpx;
		background-color: #f5f5f5;
	}
	.head{
		width: 690rpx;
		height: 66rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.head p{
		font-size: 26rpx;
		color: #999999;
	}
	.process{
		width: 690rpx;
		height: 160rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.process_top{
		width: 690rpx;
		height: 100rpx;
		display: flex;
	}
	.img1{
		width: 60rpx;
		height: 60rpx;
		margin-top: 24rpx;
		margin-left: 56rpx;
	}
	.dotted_line{
		width: 200rpx;
		height: 2rpx;
		border-bottom: 1px dashed #999999;
		margin-left: 4rpx;
		margin-top: 54rpx;
	}
	.img2{
		width: 60rpx;
		height: 60rpx;
		margin-top: 24rpx;
		margin-left: 4rpx;
	}
	.img3{
		width: 60rpx;
		height: 60rpx;
		margin-top: 24rpx;
		margin-left: 4rpx;
	}
	.process_bottom{
		width: 690rpx;
		height: 50rpx;
		display: flex;
	}
	.text1{
		font-size: 24rpx;
		color: #ff6100;
		margin-left: 16rpx;
		display: block;
	}
	.text2{
		font-size: 24rpx;
		margin-left: 120rpx;
		display: block;
	}
	.text3{
		font-size: 24rpx;
		margin-left: 148rpx;
		display: block;
	}
	.certified_enterprise{
		width: 690rpx;
		height: 87rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.certified_enterprise p{
		font-size: 28rpx;
		color: #ff6100;
	}
	/* 法人代表  姓名  身份证号 */
	.legal_person{
		width: 690rpx;
		height: 260rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	/* 是否是法人代表 */
	.invoice_type{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
	}
	.invoice_type_content{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.type{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.ordinary{
		margin-left: 78rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.increment{
		margin-left: 78rpx;
		font-size: 26rpx;
		color: #999999;
	}
	.invoice_type image{
		margin-top: 2rpx;
		/* margin-left: 190rpx; */
		width: 22rpx;
		height: 22rpx;
	}
	/* 企业法人姓名 */
	.name{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.name p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.name input{
		font-size: 26rpx;
		margin-left: 104rpx;
		color: #999999;
	}
	/* 企业法人身份证号 */
	.id_number{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.id_number p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.id_number input{
		font-size: 26rpx;
		margin-left: 52rpx;
		color: #999999;
	}
	/* 身份证上传 */
	.id_card_upload{
		width: 690rpx;
		height: 366rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.id_card_upload_top{
		width: 630rpx;
		height: 86rpx;
		display: flex;
		align-items: center;
		margin: 0 auto;
	}
	.id_card_upload_top p{
		font-size: 26rpx;
	}
	.id_card_upload_bottom{
		width: 630rpx;
		height: 250rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
	}
	.human_face{
		width: 300rpx;
		height: 250rpx;
		background-color: #f5f5f5;
		border-radius: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.human_face image{
		width: 178rpx;
		height: 106rpx;
		margin-top: 68rpx;
	}
	.human_face p{
		font-size: 24rpx;
		margin-top: 20rpx;
	}
	.national_emblem{
		width: 300rpx;
		height: 250rpx;
		background-color: #f5f5f5;
		border-radius: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.national_emblem image{
		width: 178rpx;
		height: 106rpx;
		margin-top: 68rpx;
	}
	.national_emblem p{
		font-size: 24rpx;
		margin-top: 20rpx;
	}
	/* 企业名称等 */
	.enterprise{
		width: 690rpx;
		height: 172rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.enterprise_name{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.enterprise_name p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.enterprise_name input{
		font-size: 26rpx;
		margin-left: 156rpx;
		color: #999999;
	}
	.unified_social_credit_code{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.unified_social_credit_code p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.unified_social_credit_code input{
		font-size: 26rpx;
		margin-left: 52rpx;
		color: #999999;
	}
	/* 营业执照上传 */
	.business_license{
		width: 690rpx;
		height: 400rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.business_license_top{
		width: 630rpx;
		height: 118rpx;
		margin: 0 auto;
		/* background-color: aqua; */
		overflow: hidden;
	}
	.business_license_top p{
		font-size: 26rpx;
		margin-top: 26rpx;
	}
	.business_license_top text{
		font-size: 24rpx;
		color: #999999;
	}
	.business_license_bottom{
		width: 630rpx;
		height: 250rpx;
		margin: 0 auto;
	}
	.upload_business_license{
		width: 300rpx;
		height: 250rpx;
		background-color: #f5f5f5;
		border-radius: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.upload_business_license image{
		width: 178rpx;
		height: 106rpx;
		margin-top: 68rpx;
	}
	.upload_business_license p{
		font-size: 24rpx;
		margin-top: 20rpx;
	}
	/* 企业授权书 */
	.enterprise_power_attorney{
		width: 690rpx;
		height: 400rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.enterprise_power_attorney_top{
		width: 630rpx;
		height: 118rpx;
		margin: 0 auto;
		/* background-color: aqua; */
		overflow: hidden;
	}
	.enterprise_power_attorney_top p{
		font-size: 26rpx;
		margin-top: 26rpx;
	}
	.enterprise_power_attorney_top text{
		font-size: 24rpx;
		color: #999999;
	}
	.download{
		color: #ff6100;
	}
	.enterprise_power_attorney_bottom{
		width: 630rpx;
		height: 250rpx;
		margin: 0 auto;
	}
	.upload_enterprise_power_attorney{
		width: 300rpx;
		height: 250rpx;
		background-color: #f5f5f5;
		border-radius: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.upload_enterprise_power_attorney image{
		width: 178rpx;
		height: 106rpx;
		margin-top: 68rpx;
	}
	.upload_enterprise_power_attorney p{
		font-size: 24rpx;
		margin-top: 20rpx;
	}
	/* 法人手机号码 验证码 */
	.phone{
		width: 690rpx;
		height: 172rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 20rpx;
	}
	.telephone{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.telephone p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.telephone input{
		font-size: 26rpx;
		margin-left: 104rpx;
		color: #999999;
	}
	.verification_code{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.verification_code p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.verification_code input{
		width: 190rpx;
		font-size: 26rpx;
		color: #999999;
		margin-left: 130rpx;
	}
	.verification_code text{
		margin-left: 50rpx;
		font-size: 26rpx;
		color: #ff6100;
	}
	.agreement{
		width: 690rpx;
		height: 100rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.agreement text{
		font-size: 24rpx;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 28rpx;
		font-weight: 900;
	}
</style>