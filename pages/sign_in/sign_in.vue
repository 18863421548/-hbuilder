<template>
	<view class="whole">
		<view class="logo">
			<image src="../../static/logo.jpg" mode=""></image>
		</view>
		<view class="sign_in">
			<view :class="activite==1?'mobile_login':'click_mobile_login'" @click="ckeckIndex(1)">
				<p>手机快捷登录</p>
			</view>
			<view class="shuxian"></view>
			<view :class="activite==2?'account_login':'click_account_login'" @click="ckeckIndex(2)">
				<p>账号密码登录</p>
			</view>
		</view>
		<!-- 这是验证码登录 -->
		<view class="input1" v-show="activite==1">
			<image src="../../static/dl1.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="text" v-model="phone" placeholder="请输入您的手机号账号">
		</view>
		<view class="input2" v-show="activite==1">
			<image src="../../static/dl2.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="text" v-model="sms" placeholder="请输入短信验证码">
			<text @click="code()">{{!codeTime?'获取验证码':codeTime+'s'}}</text>
		</view>
		<!-- 这是账号密码登录 -->
		<view class="input1" v-show="activite==2">
			<image src="../../static/dl1.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="text" v-model="phone1" placeholder="请输入您的手机号账号">
		</view>
		<view class="input2" v-show="activite==2">
			<image src="../../static/dl2.jpg" mode=""></image>
			<view class="xian"></view>
			<input type="password" v-model="pwd" placeholder="请输入登录密码">
			<!-- <text>获取验证码</text> -->
		</view>
		
		<view class="body">
			<p @click="register">还没有账号，立即注册</p>
			<text @click="wjmm">忘记密码</text>
		</view>
		<button @click="sub()" class="but">立 即 登 录</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				activite:1,
				phone:'',
				phone1:'',
				sms:'',
				pwd:'',
				selfChecked: false,
				codeTime:0,
			}
		},
		methods:{
			ckeckIndex(e){
				this.activite=e
			},
			// 注册
			register(){
				uni.navigateTo({
					url:"./register"
				})
			},
			// 忘记密码
			wjmm(){
				uni.navigateTo({
					url:"/pages/my/set/account/forget_password"
				})
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
						url: this.host+'/api/login/index', //仅为示例，并非真实接口地址。
						data: {
								phone:this.phone,
								phone1:this.phone1,
								code:this.sms,
								pwd:this.pwd,
								type:this.activite,
						},
						method:"post",
						success: (res) => {
								//缓存
								uni.setStorageSync('userInfo', res.data.data);
								
								uni.showToast({
									title: res.data.msg,
									icon:'none',
									duration: 3000
								});
								if(res.data.code == 1){
									setTimeout(function () {
										uni.switchTab({
											url: '../my/my',
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
		background-color: #fefefe;
	}
	.logo{
		width: 750rpx;
		height: 409rpx;
		/* background-color: aqua; */
		display: flex;
		justify-content: center;
	}
	.logo image{
		width: 286rpx;
		height: 230rpx;
		margin-top: 100rpx;
	}
	.sign_in{
		width: 630rpx;
		height: 95rpx;
		/* background-color: chartreuse; */
		margin: 0 auto;
		border-bottom: 1px solid #555555;
		display: flex;
		align-items: center;
	}
	.mobile_login{
		width: 315rpx;
		height: 95rpx;
		display: flex;
		justify-content: center;
	}
	.mobile_login p{
		width: 180rpx;
		height: 93rpx;
		font-size: 30rpx;
		color: #ff6100;
		border-bottom: 2px solid #ff6100;
		display: flex;
		align-items: center;
	}
	.click_mobile_login{
		width: 315rpx;
		height: 95rpx;
		display: flex;
		justify-content: center;
	}
	.click_mobile_login p{
		width: 180rpx;
		height: 93rpx;
		font-size: 30rpx;
/* 		color: #ff6100;
		border-bottom: 2px solid #ff6100; */
		display: flex;
		align-items: center;
	}
	
	.shuxian{
		width: 2rpx;
		height: 40rpx;
		background-color: #555555;
	}
	.account_login{
		width: 315rpx;
		height: 95rpx;
		display: flex;
		justify-content: center;
	}
	.account_login p{
		width: 180rpx;
		height: 93rpx;
		font-size: 30rpx;
		color: #ff6100;
		border-bottom: 2px solid #ff6100;
		display: flex;
		align-items: center;
	}
	.click_account_login{
		width: 315rpx;
		height: 95rpx;
		display: flex;
		justify-content: center;
	}
	.click_account_login p{
		width: 180rpx;
		height: 93rpx;
		font-size: 30rpx;
	/* 	color: #ff6100;
		border-bottom: 2px solid #ff6100; */
		display: flex;
		align-items: center;
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
	.xian{
		width: 2rpx;
		height: 30rpx;
		background-color: #555555;
		margin-left: 26rpx;
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
	.body{
		width: 630rpx;
		height: 71rpx;
		margin: 0 auto;
		margin-top: 26rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.body p{
		font-size: 24rpx;
		color: #555555;
	}
	.body text{
		font-size: 24rpx;
		color: #ff6100;
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