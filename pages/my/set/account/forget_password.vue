<template>
	<view class="whole">
		<view class="head">
			<p>备注：密码由6-20个英文字母，数字或者符号组成</p>
		</view>
		<view class="password">
			<view class="phone_number">
				<p>手机号码</p>
				<input type="text" v-model="phone" placeholder="请输入手机号码">
			</view>
			<view class="verification_code">
				<p>验证码</p>
				<input type="text" v-model="sms" placeholder="请输入验证码">
				<text @click="code()">{{!codeTime?'获取验证码':codeTime+'s'}}</text>
			</view>
			<view class="new_password">
				<p>新密码</p>
				<input type="password" v-model="password" placeholder="请输入新密码">
			</view>
			<view class="confirm_password">
				<p>确认密码</p>
				<input type="password" v-model="password22" placeholder="再次输入新密码">
			</view>
		</view>
		<button @click="sub" class="but">完成</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{

				phone:'',

				sms:'',
				password:'',
				password22:'',
				selfChecked: false,
				codeTime:0,
			}
		},
		methods:{
			ckeckIndex(e){
				this.activite=e
			},
			
			selfChangde(e) {
				this.selfChecked = !this.selfChecked;
			},
			//短信验证码
			code(){
				var _that = this;
				let myreg = /^[1][3,4,5,6,7,8,9][0-9]{9}$/;
				if(!myreg.test(_that.phone)){
					uni.showToast({
						title: '请输入正确的手机号',
						icon:"none"
					});
					return;
				}else if(this.codeTime>0){
						uni.showToast({
							title: '不能重复获取',
							icon:"none"
						});
						return;
				}else{
						this.codeTime = 60
						let timer = setInterval(()=>{
							this.codeTime--;
							if(this.codeTime<1){
								clearInterval(timer);
								this.codeTime = 0
							}
						},1000)
						uni.request({
								url: this.host+'/api/index/sms', //仅为示例，并非真实接口地址。
								data: {
										mobile:this.phone,
								},
								method:"post",
								success: (res) => {
										uni.showToast({
											title: res.data.msg,
											icon:'none',
											duration: 3000
										});
								}
						});
				}
			},
			/*提交*/
			sub(){
				uni.request({
						url: this.host+'/api/login/wjmm', //仅为示例，并非真实接口地址。
						data: {
								tel:this.phone,
					
								yzm:this.sms,
								password:this.password,
								password22:this.password22,
						},
						method:"post",
						success: (res) => {
								
								uni.showToast({
									title: res.data.msg,
									icon:'none',
									duration: 3000
								});
								if(res.data.code == 1){
									setTimeout(function () {
										uni.redirectTo({
											url: '/pages/sign_in/sign_in',
										})
									}, 3000);
								
								}
					 
						}
				});
			
			}
		}
	}
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #f5f5f5;
	}
	.head{
		width: 690rpx;
		height: 63rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.head p{
		font-size: 24rpx;
	}
	.password{
		width: 690rpx;
		height: 347rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
	}
	.phone_number{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.phone_number p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.phone_number input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 60rpx;
	}
	.verification_code{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.verification_code p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.verification_code input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 86rpx;
	}
	.verification_code text{
		margin-left: 26rpx;
		font-size: 26rpx;
		color: #ff6100;
	}
	.new_password{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc;
		display: flex;
		align-items: center;
	}
	.new_password p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.new_password input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 86rpx;
	}
	.confirm_password{
		width: 650rpx;
		height: 86rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
	}
	.confirm_password p{
		font-size: 26rpx;
		margin-left: 10rpx;
	}
	.confirm_password input{
		font-size: 26rpx;
		color: #999999;
		margin-left: 60rpx;
	}
	.but{
		width: 690rpx;
		height: 88rpx;
		background-color: #ff6100;
		border-radius: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		color: #fff;
		font-size: 28rpx;
		margin-top: 100rpx;
		font-weight: 900;
	}
</style>