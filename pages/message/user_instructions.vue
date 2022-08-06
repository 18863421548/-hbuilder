<template>
	<view class="whole">
		<view class="head">
			<p>用户签收注意事项</p>
		</view>
		<view class="box1">
			<text>
				<span class="xing">* </span><span class="tips">重要提示：</span>客户在收件时务必本人当场验收，如发现包装或设
				备破损需在快递员在场时马上联系悟空优租客服协助处理，如客
				户已签收则表示客户已对设备验收无误：
			</text>
		</view>
		<view class="box1">
				<span class="xing">* </span>
				<span class="proposal">建议保留包装纸箱以备还机时使用；</span>
		</view>
		<view class="box1">
			<text>
				客户在收货时应首先确认外包装是否完好，如有破损、变形、被污染等可能影响包装内设备质量的问题应向快递送货人员指出并多角度拍照保存；然后打开包装对设备外观和性能进行测试
			</text>
		</view>
		<view class="box1">
			<p class="one">一、全新机的签收</p>
		</view>
		<view class="box1">
			<text>1. 悟空优租使用的全新机均为原厂包装（除应客户要求进行配置或其他需要开箱处理的需求外），请首先确认原厂包装的完好；</text>
		</view>
		<view class="box1">
			<text>2. 全新机外观无变形、划痕等损伤及其它使用痕迹，原厂包装膜等完好；根据包装箱内说明确认配件是否齐全；</text>
		</view>
		<view class="box1">
			<text>3. 机器可正常启动进入系统或系统激活页面；屏幕无暗屏、黑屏、花线等现象；</text>
		</view>
		<view class="box1">
			<text>4. 确认设备序列号与订单序列号一致。</text>
		</view>
		<view class="box1">
			<p class="one">二、非全新设备的签收</p>
		</view>
		<view class="box1">
			<text>1. 设备包装可能使用悟空优租包装箱或厂商包装箱，但均会使用悟空优租胶条封口，请验收时除确认包装箱体是否有损坏同时也确认胶条是否有开封的痕迹；</text>
		</view>
		<view class="box1">
			<text>2. 根据订单商品信息确认电池、电源、键盘、鼠标、连接线等配件齐全；</text>
		</view>
		<view class="box1">
			<text>3. 设备外观无裂痕、无破损、无污染；</text>
		</view>
		<view class="box1">
			<text>4. 机器可正常启动进入系统；无密码；屏幕无暗屏、黑屏、花线等现象;</text>
		</view>
		<view class="box1">
			<text>5. 确认设备序列号与订单序列号一致。</text>
		</view>
		<view class="head">
			<p>违约处理</p>
		</view>
		<view class="box1">
			<p class="ones">一、满足以下情况之一的，该使用方将被认定为失信客户：</p>
		</view>
		<view class="box1">
			<text>1. 逾期1个月不支付设备使用费；</text>
		</view>
		<view class="box1">
			<text>2. 按约定应当归还设备，但拒不归还；</text>
		</view>
		<view class="box1">
			<text>3. 在服务期结束前提前归还设备，但不按协议支付随用随还服务费或违约金；</text>
		</view>
		<view class="box1">
			<text>4. 归还的设备严重损坏，但拒不按协议偿付维修费用。</text>
		</view>
		<view class="box1">
			<p class="one">二、对于被认定为失信客户的，悟空优租将有权利采取包括但不限于以下的措施：</p>
		</view>
		<view class="box1">
			<text>1. 不接受失信客户的服务需求；</text>
		</view>
		<view class="box1">
			<text>2. 将失信客户公司信息及相应的申请人个人信息在悟空佣租网站公布；</text>
		</view>
		<view class="box1">
			<text>3. 将失信客户公司信息及相应的申请人个人信息在互联网其他网站公布；</text>
		</view>
		<view class="box1">
			<text>4. 将失信客户公司信息及相应的申请人个人信息提供给第三方机构，包括央行下属征信平台、芝麻信用等征信机构；</text>
		</view>
		<view class="box1">
			<text>5. 向公安机关报案；</text>
		</view>
		<view class="box1">
			<text>6.向法院起诉，并依照相关法律规定，报请将失信客户的身份信息及相关公司信息至中国人民共和国全国法院被执行人信息网公布。</text>
		</view>
		<view class="box2">
			<text>因悟空优租对失信客户采取的任何措施给失信客户带来的任何损失，均由该使用方自行承担，悟空优租概不负责。</text>
		</view>
		<view class="box2">
			<text>对于任何无法按合约履行的情况，欢迎双方友好协商解决，尽量避免发生信用违约，请致电 0531-55697114.</text>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.whole{
		width: 100%;
		height: 2650rpx;
		background-color: #f9f9f9;
	}
	.head{
		width: 750rpx;
		height: 96rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 28rpx;
		color: #ff6100;
	}
	.box1{
		display: flex;
		width: 690rpx;
		margin: 0 auto;
	}
	.xing{
		font-size: 28rpx;
		color: #e73c31;
	}
	.tips{
		font-size: 26rpx;
		font-weight: 600;
		margin-left: 4rpx;
	}
	.box1 text{
		font-size: 24rpx;
		display: flex;
		line-height: 46rpx;
	}
	.proposal{
		font-size: 24rpx;
		margin-left: 4rpx;
	}
	.one{
		/* margin-top: 10rpx; */
		height: 120rpx;
		/* background-color: aqua; */
		display: flex;
		align-items: center;
	}
	.ones{
		/* margin-top: 40rpx; */
	}
	.box2{
		display: flex;
		width: 690rpx;
		margin: 0 auto;
	}
	.box2 text{
		font-size: 24rpx;
		line-height: 46rpx;
		color: #e73c31;
	}
</style>