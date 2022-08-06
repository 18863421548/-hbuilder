<template>
	<view class="whole">
		<view class="head">
			完善补充信息
		</view>
		<!-- 一般纳税人证明 -->
		<view class="box1">
			<view class="box1_content">
				<p>一般纳税人证明:</p>
				<text>为了确保您的企业具备开票资格，请上传您的一般纳税人的证明</text>
				<view class="img" @click="generalTaxpayer">
					<image src="../../../../static/信息.jpg" mode=""></image>
					<!-- <image v-for="item in imgArr" :src="item"></image> -->
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 征信报告 -->
		<view class="box1">
			<view class="box1_content">
				<p>征信报告:</p>
				<text>15天内的个人或法定代表人/企业征信报告（人民银行网页简版和完整版都可）</text>
				<view class="img" @click="creditReport">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 社保证明 -->
		<view class="box2">
			<view class="box2_content">
				<p>社保证明:</p>
				<text>近连续3个月员工（或个人）社保缴纳记录（不接受Excel版本的，需要社保局拉取或者社保网站截图，能清晰看到企业名称（个人姓名）和社保缴纳总人数</text>
				<view class="img" @click="socialSecurity">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 资金流水 -->
		<view class="box3">
			<view class="box3_content">
				<p>资金流水:</p>
				<text>近连续3个月企业对公银行流水（或个人银行流水）（不接受Excel和隐去重要信息的流水，需要企业在开户行拉取或企业开户行网银账户截图，能清晰看到企业名称和往来款明细）</text>
				<view class="img" @click="capitalFlow">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 经营场地 -->
		<view class="box1">
			<view class="box1_content">
				<p>经营场地:</p>
				<text>经营场地照片、场地经营合同（场地照片包含门头，整个办公区域，清晰看到loge，工位数）</text>
				<view class="img" @click="businessSite">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 缴费证明 -->
		<view class="box1">
			<view class="box1_content">
				<p>缴费证明:</p>
				<text>物业费、水费、电费、租金缴纳证明（缴费打款凭证、收据、发票、能清晰看到付款方和收款方）</text>
				<view class="img" @click="paymentCertificate">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 运营授权书 -->
		<view class="box4">
			<view class="box4_content">
				<p>运营授权书:</p>
				<text>需加盖企业公章、本人签字。然后拍照上传。</text>
				<view class="img" @click="operationAuthorization">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<view class="separate"></view>
		<!-- 其他 -->
		<view class="box5">
			<view class="box5_content">
				<p>其他:</p>
				<view class="img" @click="other">
					<image src="../../../../static/信息.jpg" mode=""></image>
				</view>
			</view>
		</view>
		<button class="but">立即提交</button>
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
			// 一般纳税人证明
			generalTaxpayer(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 征信报告
			creditReport(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 社保证明
			socialSecurity(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 资金流水
			capitalFlow(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 经营场地
			businessSite(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 缴费证明
			paymentCertificate(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 运营授权书
			operationAuthorization(){
				uni.chooseImage({
					count:1,
					success:res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			// 其他
			other(){
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
		width: 750rpx;
		height: 3110rpx;
		background-color: #f5f5f5;
	}
	.head{
		width: 690rpx;
		height: 88rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		font-size: 28rpx;
		color: #ff6100;
	}
	.box1{
		width: 690rpx;
		height: 344rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.box1_content{
		width: 630rpx;
		height: 344rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.box1_content p{
		font-size: 26rpx;
		margin-top: 28rpx;
	}
	.box1_content text{
		font-size: 24rpx;
		color: #999999;
		display: block;
		margin-top: 14rpx;
	}
	.img{
		width: 240rpx;
		height: 160rpx;
		background-color: #f5f5f5;
		border-radius: 10px;
		margin-top: 16rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.img image{
		width: 68rpx;
		height: 68rpx;
	}
	.separate{
		width: 750rpx;
		height: 20rpx;
	}
	/* 社保证明 */
	.box2{
		width: 690rpx;
		height: 374rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.box2_content{
		width: 630rpx;
		height: 374rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.box2_content p{
		font-size: 26rpx;
		margin-top: 28rpx;
	}
	.box2_content text{
		font-size: 24rpx;
		color: #999999;
		display: block;
		margin-top: 14rpx;
	}
	/* 资金流水 */
	.box3{
		width: 690rpx;
		height: 406rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.box3_content{
		width: 630rpx;
		height: 406rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.box3_content p{
		font-size: 26rpx;
		margin-top: 28rpx;
	}
	.box3_content text{
		font-size: 24rpx;
		color: #999999;
		display: block;
		margin-top: 14rpx;
	}
	/* 运营授权书 */
	.box4{
		width: 690rpx;
		height: 309rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.box4_content{
		width: 630rpx;
		height: 309rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.box4_content p{
		font-size: 26rpx;
		margin-top: 28rpx;
	}
	.box4_content text{
		font-size: 24rpx;
		color: #999999;
		display: block;
		margin-top: 14rpx;
	}
	/* 其他 */
	.box5{
		width: 690rpx;
		height: 266rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.box5_content{
		width: 630rpx;
		height: 266rpx;
		margin: 0 auto;
		overflow: hidden;
	}
	.box5_content p{
		font-size: 26rpx;
		margin-top: 28rpx;
	}
	/* 立即提交 */
	.but{
		width: 690rpx;
		height: 88rpx;
		border-radius: 40rpx;
		background-color: #ff6100;
		color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 30rpx;
		font-size: 28rpx;
		font-weight: 900;
	}
	
	
	
	
	
</style>