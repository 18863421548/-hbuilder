<template>
	<view class="whole">
		<view class="logo">
			<image src="../../static/logo.jpg" mode=""></image>
		</view>
		<view class="input1">
			<image src="../../static/注册1.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="text" name="mobile"  v-model="mobile" placeholder="请输入您的手机号">
		</view>
		<view class="input2">
			<image src="../../static/注册2.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="text" placeholder="请输入短信验证码"  v-model="sms" >
			<text @click="code()">{{!codeTime?'获取验证码':codeTime+'s'}}</text>
		</view>
		<view class="input1">
			<image src="../../static/注册3.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="password" placeholder="请设置登录密码"  v-model="password">
		</view>
		<view class="input1">
			<image src="../../static/注册3.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="password" placeholder="请再次输入确认密码"  v-model="password_two">
		</view>
		<view class="agreement">
			<u-checkbox-group @change="selfChangde">
				<u-checkbox  :checked="selfChecked" shape="square" label=""></u-checkbox>
			</u-checkbox-group>
			<p>我已阅读并同意</p>
			<text>《条款和协议》</text>
			<span>*</span>
		</view>
		<button class="but" @click="sub()" >立 即 登 录</button>
	</view>
</template>

<script>
	 export default {
		  data() {
				return {
					mobile: '',
					sms: '',
					password: '',
					password_two: '',
					selfChecked: false,
					codeTime:0,
				}
			},
	    onLoad(){
					
	    },
			methods: {  
				selfChangde(e) {
					this.selfChecked = !this.selfChecked;
				},
				//短信验证码
				code(){
					
					var _that = this;
					let myreg = /^[1][3,4,5,6,7,8,9][0-9]{9}$/;
					if(!myreg.test(_that.mobile)){
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
											mobile:this.mobile,
									},
									method:"post",
									success: (res) => {
											uni.showToast({
												title: res.data.msg,
												icon:'none',
												duration: 3000
											});
											if(res.data.code == 1001){
												
											}
											
								 
									}
							});
					}
				},
				sub(){  

					if(!this.selfChecked){
						uni.showToast({
							title: '请先勾选协议',
							icon:'none',
							duration: 3000
						});
					}else{
						uni.request({
								url: this.host+'/api/register/index', //仅为示例，并非真实接口地址。
								data: {
										tel:this.mobile,
										yzm:this.sms,
										password:this.password,
										password22:this.password_two,
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
													url: '/pages/sign_in/sign_in'
												})
											}, 3000);
											;
										}
							 
								}
						});
					}
				}  
			}  
			
	  }
	
</script>

<style>
	.whole{
		width: 100%;
		height: 1246rpx;
		background-color: #fefefe;
	}
	.logo{
		width: 750rpx;
		height: 400rpx;
		display: flex;
		justify-content: center;
	}
	.logo image{
		width: 286rpx;
		height: 230rpx;
		margin-top: 100rpx;
	}
	
	
	.xian{
		width: 2rpx;
		height: 30rpx;
		background-color: #555555;
		margin-left: 26rpx;
	}
	.input1{
		width: 630rpx;
		height: 80rpx;
		border: 1px solid #999999;
		border-radius: 20px;
		margin: 0 auto;
		margin-top: 30rpx;
		display: flex;
		align-items: center;
	}
	.input1 image{
		width: 26rpx;
		height: 28rpx;
		margin-left: 30rpx;
	}
	.input1 input{
		font-size: 24rpx;
		color: #999999;
		margin-left: 26rpx;
	}
	.input2{
		width: 630rpx;
		height: 80rpx;
		border: 1px solid #999999;
		border-radius: 20px;
		margin: 0 auto;
		margin-top: 30rpx;
		display: flex;
		align-items: center;
	}
	.input2 image{
		width: 26rpx;
		height: 28rpx;
		margin-left: 30rpx;
	}
	.input2 input{
		font-size: 24rpx;
		color: #999999;
		margin-left: 26rpx;
	}
	.input2 text{
		font-size: 24rpx;
		color: #ff6100;
		margin-left: 100rpx;
	}
	.agreement{
		width: 630rpx;
		height: 71rpx;
		margin: 0 auto;
		margin-top: 26rpx;
		display: flex;
		align-items: center;
		font-size: 24rpx;
	}
	.agreement p{
		color: #555555;
	}
	.agreement text{
		color: #ff6100;
	}
	.agreement span{
		color: #ff0000;
	}
	.but{
		width: 630rpx;
		height: 80rpx;
		border-radius: 40rpx;
		margin: 0 auto;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #ff6100;
		color: #fff;
		font-size: 30rpx;
		font-weight: 900;
	}
</style>