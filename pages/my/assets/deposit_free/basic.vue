<template>
	<view class="whole">
		<view class="head">
			<p>基本信息</p>
		</view>
		<!-- 法人姓名 及 身份证号 -->
		<view class="legal_person">
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
		<!-- 法人手机号 电子邮箱 -->
		<view class="legal_person">
			<view class="telephone">
				<p>法人手机号码</p>
				<input type="text" placeholder="请输入法人手机号码">
			</view>
			<view class="e_mail">
				<p>电子邮箱</p>
				<input type="text" placeholder="请输入电子邮箱">
			</view>
		</view>
		<!-- 保存 -->
		<button class="but">保存</button>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				imgArr:[],
			}
		},
		methods:{
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
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 1630rpx;
		background-color: #f9f9f9;
		overflow: hidden;
	}
	.head p{
		font-size: 28rpx;
		color: #ff6100;
		margin-left: 30rpx;
		margin-top: 35rpx;
	}
	/* 法人姓名 及 身份证号 */
	.legal_person{
		width: 690rpx;
		height: 172rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 22rpx;
	}
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
	/* 法人手机号码 电子邮箱 */
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
	.e_mail{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.e_mail p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.e_mail input{
		font-size: 26rpx;
		margin-left: 156rpx;
		color: #999999;
	}
	/* 保存 */
	.but{
		width: 690rpx;
		height: 88rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 50rpx;
		font-size: 28rpx;
		font-weight: 900;
	}
</style>