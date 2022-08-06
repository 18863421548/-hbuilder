<template>
	<view>
		<view class="nav">
			<view :class="activite==1?'this_month':'click_this_month'" @click="ckeckIndex(1)">
				<p>本月代缴</p>
			</view>
			<view :class="activite==2?'next_month':'click_next_month'" @click="ckeckIndex(2)">
				<p>下月及以后代缴</p>
			</view>
			<view :class="activite==3?'paid_bill':'click_paid_bill'" @click="ckeckIndex(3)">
				<p>已缴账单</p>
			</view>
		</view>
		<!-- 本月代缴 -->
		<view class="head" v-show="activite==1">
			<view class="need_pay">
				<p>当前需支付 (元)</p>
				<text>6705.00</text>
				<button>缴清当月账单</button>
			</view>
			<view class="tips">
				每个账单的最迟缴费日为订单起租日同日
			</view>
		</view>
		<view class="body" v-show="activite==1" v-for="item in list1">
			<view class="body_content">
				<view class="body_content_left">
					<p>{{item.name}}</p>
					<text>{{item.time}}</text>
					<text>{{item.quantity}}</text>
				</view>
				<view class="body_content_right">
					<p>{{item.state}}</p>
					<image src="../../../../static/向右箭头.png" mode=""></image>
				</view>
			</view>
		</view>
		<!-- 下月及以后代缴 -->
		<view class="head" v-show="activite==2">
			<view class="total">
				本账户待缴费用总计: ￥49974.2
			</view>
			<view class="need_pay_next">
				<p>当前需支付 (元)</p>
				<text>0.00</text>
				<button>缴清当月账单</button>
			</view>
			<view class="tips">
				每个账单的最迟缴费日为订单起租日同日
			</view>
		</view>
		<!-- 全选 -->
		<view class="select_all" v-show="activite==2">
			<checkbox-group name="allCheck" @change="changeAll" class="allCheck">
				<label>
					<checkbox :value="allCheck.value" :checked="allCheck.checked" style="transform:scale(0.7)" />
					<text>{{allCheck.name}}</text>
				</label>
			</checkbox-group>
		</view>
		<!-- 每项选择 -->
		<checkbox-group name="check" @change="changeCheck" class="check" v-show="activite==2">
			<label v-for="(item, index) in content" :key="item.id">
				<view class="single_choice">
					<view class="single_choice_content">
						<checkbox :value="item.value" :checked="item.checked" style="transform:scale(0.7)" />
						<view class="single_choice_left">
							<p>{{item.name}}</p>
							<text>{{item.time}}</text>
							<text>{{item.quantity}}</text>
						</view>
						<view class="single_choice_right">
							<p>{{item.state}}</p>
							<image src="../../../../static/向右箭头.png" mode=""></image>
						</view>
					</view>
				</view>
			</label>
		</checkbox-group>
		<!-- 已缴账单 -->
		<view class="paid_bill_content" v-for="item in list2" v-show="activite==3" @click="details(4)">
			<view class="paid_bill_content_middle">
				<view class="paid_bill_content_middle_left">
					<image src="../../../../static/dn.jpg" mode=""></image>
					<view class="paid_bill_content_middle_left_data">
						<p>{{item.name}}</p>
						<text>{{item.time}}</text>
						<text>{{item.quantity}}</text>
					</view>
				</view>
				<view class="paid_bill_content_middle_right">
					<p>{{item.state}}</p>
					<image src="../../../../static/向右箭头.png" mode=""></image>
				</view>
			</view>
		</view>

		<!-- 已缴详情 -->
		<view class="details_head" v-show="activite==4">
			<view class="time">
				<p>请选择年月</p>
				<picker class="choice" mode="date" :value="date" :start="startDate" :end="endDate" @change="bindDateChange">
					<view class="year"><!-- {{date}} -->年 / 月 / 日</view>
					<image src="../../../../static/日历.jpg" mode=""></image>
				</picker>
			</view>
		</view>
		<view class="details_body" v-for="item in list3" v-show="activite==4">
			<view class="details_body_content">
				<view class="details_body_content_left">
					<p>{{item.time}}</p>
					<text>{{item.times}}</text>
				</view>
				<view class="details_body_content_right">
					<p>{{item.state}}</p>
					<image src="../../../../static/向右箭头.png" mode=""></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	function getDate(type) {
		const date = new Date();
		let year = date.getFullYear();
		let month = date.getMonth() + 1;
		let day = date.getDate();

		if (type === 'start') {
			year = year - 10;
		} else if (type === 'end') {
			year = year + 10;
		}
		month = month > 9 ? month : '0' + month;
		day = day > 9 ? day : '0' + day;

		return `${year} / ${month} / ${day}`;
	}
	export default {
		data() {
			return {
				// 日期
				date: getDate({
					format: true
				}),
				startDate: getDate('start'),
				endDate: getDate('end'),
				// 日期
				activite: 1,
				list1: [{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20   2期",
						state: "已退租"
					},
					{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20   2期",
						state: "租赁中"
					},
					{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20   2期",
						state: "已逾期"
					}
				],
				list2: [{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20 2期",
						state: "已退租"
					},
					{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20 2期",
						state: "租赁中"
					},
					{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20 2期",
						state: "租赁中"
					}
				],
				list3: [{
						time: "2022-06-01~2022-06-30",
						times:"2022-07-22",
						state: "已支付"
					},
					{
						time: "2022-06-01~2022-06-30",
						times:"2022-07-22",
						state: "已支付"
					},
					{
						time: "2022-06-01~2022-06-30",
						times:"2022-07-22",
						state: "已支付"
					}
				],
				allCheck: {
					name: '全选',
					value: 'all',
					checked: false
				},
				content: [{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20   2期",
						state: "租赁中",
						value: '1',
						id: 1,
						whether: true
					},
					{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20   2期",
						state: "租赁中",
						value: '2',
						id: 2,
						whether: true
					},
					{
						name: "iMac ME088CH 一体机",
						time: "2022-07-24前必须缴清",
						quantity: "数量:  x  20   2期",
						state: "租赁中",
						value: '3',
						id: 3,
						whether: true
					}
				]
			}
		},
		methods: {
			ckeckIndex(e) {
				this.activite = e
			},
			// 全选
			changeAll: function(e) {
				if (e.detail.value.length == 0) {
					this.content.map(item => this.$set(item, 'checked', false));
					this.$set(this.allCheck, 'checked', false);
				} else {
					this.content.map(item => this.$set(item, 'checked', true));
					this.$set(this.allCheck, 'checked', true);
				}
			},
			// 多选
			changeCheck: function(e) {
				var items = this.content;
				var len = this.content.length;
				var values = e.detail.value;
				// console.log(values)
				for (var i = 0; i < len; i++) {
					var item = items[i];
					if (values.includes(item.value)) {
						this.$set(item, 'checked', true);
					} else {
						this.$set(item, 'checked', false);
					}
				}
				// 判断选中状态
				var arr = [];
				this.content.forEach(item => item.whether == true ? arr.push(item) : '');
				var isAll = arr.every(item => item.checked == true);
				isAll ? this.$set(this.allCheck, 'checked', true) : this.$set(this.allCheck, 'checked', false)
			},
			details(e) {
				this.activite = e
			},
			// 日期
			bindDateChange: function(e) {
				this.date = e.detail.value;
			}
		}
	}
</script>

<style>
	.nav {
		width: 750rpx;
		height: 88rpx;
		background-color: #ff6200;
		display: flex;
		justify-content: space-around;
	}

	.this_month {
		width: 120rpx;
		height: 88rpx;
	}

	.this_month p {
		width: 120rpx;
		height: 84rpx;
		font-size: 26rpx;
		color: #fff;
		border-bottom: 2px solid #fff;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.click_this_month {
		width: 120rpx;
		height: 88rpx;
		font-size: 26rpx;
		color: #ffd8cb;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.next_month {
		width: 200rpx;
		height: 88rpx;
	}

	.next_month p {
		width: 200rpx;
		height: 84rpx;
		font-size: 26rpx;
		color: #fff;
		border-bottom: 2px solid #fff;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.click_next_month {
		width: 200rpx;
		height: 88rpx;
		font-size: 26rpx;
		color: #ffd8cb;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.paid_bill {
		width: 120rpx;
		height: 88rpx;
	}

	.paid_bill p {
		width: 120rpx;
		height: 84rpx;
		font-size: 26rpx;
		color: #fff;
		border-bottom: 2px solid #fff;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.click_paid_bill {
		width: 120rpx;
		height: 88rpx;
		font-size: 26rpx;
		color: #ffd8cb;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.head {
		width: 750rpx;
		height: 470rpx;
		background: linear-gradient(#ff6301, #fe9011);
		overflow: hidden;
	}

	.need_pay {
		width: 690rpx;
		height: 350rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		margin-top: 59rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.need_pay p {
		font-size: 26rpx;
		font-weight: 900;
		margin-top: 70rpx;
	}

	.need_pay text {
		font-size: 50rpx;
		font-weight: 900;
		margin-top: 38rpx;
	}

	.need_pay button {
		width: 400rpx;
		height: 65rpx;
		background-color: #ff6100;
		border-radius: 40rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 24rpx;
		color: #fff;
		margin-top: 50rpx;
	}

	.tips {
		width: 690rpx;
		height: 60rpx;
		margin: 0 auto;
		color: #fff;
		font-size: 20rpx;
		display: flex;
		align-items: center;
		justify-content: flex-end;
	}

	.body {
		width: 750rpx;
		height: 162rpx;
		border-bottom: 1px solid #cccccc;
	}

	.body_content {
		width: 690rpx;
		height: 162rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.body_content_left {
		width: 300rpx;
		height: 114rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.body_content_left p {
		font-size: 26rpx;
	}

	.body_content_left text {
		font-size: 24rpx;
		color: #999999;
	}

	.body_content_right {
		width: 95rpx;
		height: 50rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.body_content_right p {
		font-size: 24rpx;
		color: #ff6100;
	}

	.body_content_right image {
		width: 16rpx;
		height: 20rpx;
	}

	/* 下月及以后代缴 */
	.total {
		width: 690rpx;
		height: 59rpx;
		margin: 0 auto;
		font-size: 20rpx;
		color: #fff;
		display: flex;
		align-items: center;
	}

	.need_pay_next {
		width: 690rpx;
		height: 350rpx;
		background-color: #fff;
		border-radius: 10px;
		margin: 0 auto;
		/* margin-top: 59rpx; */
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.need_pay_next p {
		font-size: 26rpx;
		font-weight: 900;
		margin-top: 70rpx;
	}

	.need_pay_next text {
		font-size: 50rpx;
		font-weight: 900;
		margin-top: 38rpx;
	}

	.need_pay_next button {
		width: 400rpx;
		height: 65rpx;
		background-color: #ff6100;
		border-radius: 40rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 24rpx;
		color: #fff;
		margin-top: 50rpx;
	}

	/* 全选 */
	.select_all {
		width: 750rpx;
		height: 60rpx;
		background-color: #f5f5f5;
		display: flex;
		align-items: center;
	}

	.allCheck {
		margin-left: 30rpx;
	}

	/* 单选 */
	.single_choice {
		width: 750rpx;
		height: 162rpx;
		border-bottom: 1px solid #cccccc;
		display: flex;
		justify-content: center;
	}

	.single_choice_content {
		width: 690rpx;
		height: 162rpx;
		display: flex;
		align-items: center;
	}

	.single_choice_left {
		width: 300rpx;
		height: 114rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.single_choice_left p {
		font-size: 26rpx;
	}

	.single_choice_left text {
		font-size: 24rpx;
		color: #999999;
	}

	.single_choice_right {
		width: 95rpx;
		height: 50rpx;
		margin-left: 236rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.single_choice_right p {
		font-size: 24rpx;
		color: #ff6100;
	}

	.single_choice_right image {
		width: 16rpx;
		height: 20rpx;
	}

	/* 已缴账单 */
	.paid_bill_content {
		width: 750rpx;
		height: 162rpx;
		border-bottom: 1px solid #cccccc;
	}

	.paid_bill_content_middle {
		width: 690rpx;
		height: 162rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.paid_bill_content_middle_left {
		width: 430rpx;
		height: 162rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.paid_bill_content_middle_left image {
		width: 117rpx;
		height: 84rpx;
	}

	.paid_bill_content_middle_left_data {
		width: 292rpx;
		height: 114rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.paid_bill_content_middle_left_data p {
		font-size: 26rpx;
	}

	.paid_bill_content_middle_left_data text {
		font-size: 24rpx;
		color: #999999;
	}

	.paid_bill_content_middle_right {
		width: 95rpx;
		height: 50rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.paid_bill_content_middle_right p {
		font-size: 24rpx;
		color: #ff6100;
	}

	.paid_bill_content_middle_right image {
		width: 16rpx;
		height: 20rpx;
	}
	/* 已缴页面的详情 */
	.time{
		width: 750rpx;
		height: 95rpx;
		background: linear-gradient(#ff6301, #fe9011);
		display: flex;
		align-items: center;
	}
	.time p{
		font-size: 26rpx;
		color: #fff;
		margin-left: 30rpx;
	}
	.choice{
		width: 300rpx;
		height: 45rpx;
		border: 1px solid #fff;
		margin-left: 20rpx;
		font-size: 24rpx;
		color: #fff;
		display: flex;
		align-items: center;
		position: relative;
	}
	.year{
		margin-left: 27rpx;
	}
	.choice image{
		position: absolute;
		width: 24rpx;
		height: 24rpx;
		bottom: 10rpx;
		left: 254rpx;
	}
	.details_body{
		width: 750rpx;
		height: 125rpx;
		border-bottom: 1px solid #cccccc;
	}
	.details_body_content{
		width: 690rpx;
		height: 125rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.details_body_content_left{
		width: 320rpx;
		height: 72rpx;
	}
	.details_body_content_left p{
		font-size: 26rpx;
	}
	.details_body_content_left text{
		font-size: 24rpx;
		color: #999999;
	}
	.details_body_content_right{
		width: 95rpx;
		height: 50rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.details_body_content_right p {
		font-size: 24rpx;
		color: #999999;
	}
	
	.details_body_content_right image {
		width: 16rpx;
		height: 20rpx;
	}
</style>
