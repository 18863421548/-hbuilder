<template>
	<view>
		<view class="header">
			<view class="search">
				<input class="input" placeholder="请输入搜索内容" />
				<button class="but_one">搜索</button>
				<button class="but_two" @click="search">筛选</button>
			</view>
		</view>
		<!-- <view class="content">
			<sl-filter :themeColor="themeColor" :menuList="menuList" @result="result" v-show="!flag"></sl-filter>
		</view> -->
		<view class="nav">
			<view class="nav_bar">
				<view :class="activite==1?'bar':'index'" @click="ckeckIndex(1)">综合排序</view>
				<view :class="activite==2?'bar':'index'" @click="ckeckIndex(2)">价格由低到高</view>
				<view :class="activite==3?'bar':'index'" @click="ckeckIndex(3)">价格由高到低</view>
			</view>
		</view>
		<view class="computer_list" v-show="activite==1">
			<view class="computer" v-for="item in list">
				<image :src="item.path" mode=""></image>
				<p>{{item.name}}</p>
				<text>{{item.to_configure}}</text>
				<span>{{item.price}}</span>
			</view>
		</view>
		<view class="computer_list" v-show="activite==2">
			
		</view>
		<view class="computer_list" v-show="activite==3">
			
		</view>
	</view>
</template>

<script>
	import slFilter from "../../components/songlazy-sl-filter/sl-filter/sl-filter.vue"
	    export default {
	        components: {
	            slFilter
	        },
	        data() {
	            return {
					list:[
						{
							path:"../../static/62d1936d53fef.png",
							name:"Think Pad X13",
							to_configure:"i5-10|8G|25G|核显|13.3",
							price:"￥299/月"
						},
						{
							path:"../../static/62d1936d53fef.png",
							name:"Think Pad X13",
							to_configure:"i5-10|8G|25G|核显|13.3",
							price:"￥299/月"
						},
						{
							path:"../../static/62d1936d53fef.png",
							name:"Think Pad X13",
							to_configure:"i5-10|8G|25G|核显|13.3",
							price:"￥299/月"
						},
						{
							path:"../../static/62d1936d53fef.png",
							name:"Think Pad X13",
							to_configure:"i5-10|8G|25G|核显|13.3",
							price:"￥299/月"
						},
						{
							path:"../../static/62d1936d53fef.png",
							name:"Think Pad X13",
							to_configure:"i5-10|8G|25G|核显|13.3",
							price:"￥299/月"
						},
						{
							path:"../../static/62d1936d53fef.png",
							name:"Think Pad X13",
							to_configure:"i5-10|8G|25G|核显|13.3",
							price:"￥299/月"
						}
					],
					activite:1,
					flag:true,
	                themeColor: '#000000',
	                filterResult: '',
	                menuList: [{
	                        'title': '商品分类',
	                        'detailTitle': '请选择商品类型（单选）',
	                        'isMutiple': false,
	                        'key': 'jobType',
	                        'detailList': [{
	                                'title': '不限',
	                                'value': ''
	                            },
	                            {
	                                'title': '笔记本',
	                                'value': 'uni-app'
	                            },
	                            {
	                                'title': '台式机',
	                                'value': 'java'
	                            },
	                            {
	                                'title': '一体机',
	                                'value': 'web'
	                            },
	                            {
	                                'title': '外设配件',
	                                'value': 'Android'
	                            },
	                            {
	                                'title': '显示器',
	                                'value': 'iOS'
	                            }
	                        ]
	
	                    },
	                    {
	                        'title': '商品品牌',
	                        'key': 'salary',
	                        'isMutiple': false,
	                        'detailTitle': '请选择商品品牌（单选）',
	                        'detailList': [{
	                                'title': '不限',
	                                'value': ''
	                            },
	                            {
	                                'title': 'Thinkpad',
	                                'value': '7000~8000'
	                            },
	                            {
	                                'title': 'HP',
	                                'value': '8000~9000'
	                            },
	                            {
	                                'title': '联想',
	                                'value': '9000~10000'
	                            },
	                            {
	                                'title': '苹果',
	                                'value': '10000~1000000'
	                            }
	                        ]
	
	                    },
	                    {
	                        'title': '租金范围',
	                        'key': 'single',
	                        'isMutiple': false,
	                        'detailTitle': '请选择租金范围（单选）',
	                        'detailList': [{
	                                'title': '不限',
	                                'value': ''
	                            },
	                            {
	                                'title': '0~99元',
	                                'value': 'test_1'
	                            },
	                            {
	                                'title': '100~149元',
	                                'value': 'test_2'
	                            },
	                            {
	                                'title': '150~199元',
	                                'value': 'test_3'
	                            },
	                            {
	                                'title': '200~249元',
	                                'value': 'test_4'
	                            },
	                            {
	                                'title': '250~299元',
	                                'value': 'test_5'
	                            }
	                        ]
	                    },
	                    {
	                        'title': '新旧属性',
	                        'key': 'sort',
	                        'isSort': true,
	                        'detailList': [{
	                                'title': '不限',
	                                'value': ''
	                            },
	                            {
	                                'title': '全新设备',
	                                'value': 'add_time'
	                            },
	                            {
	                                'title': '非全新设备',
	                                'value': 'wages_up'
	                            }
	                        ]
	                    }
	                ]
	            }
	        },
	        onLoad() {
	
	        },
	        methods: {
	            result(val) {
	                console.log('filter_result:' + JSON.stringify(val));
	                this.filterResult = JSON.stringify(val, null, 2)
					this.flag=!this.flag
	            },
				search(){
					this.flag=!this.flag
				},
				ckeckIndex(e){
					this.activite=e
				}
	        }
	    }
</script>

<style>
	.header{
		width: 750rpx;
		height: 110rpx;
		background-color: #f5f5f5;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.search{
		width: 690rpx;
		height: 70rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.input{
		width: 530rpx;
		height: 70rpx;
		padding-left: 20rpx;
		border-radius: 30px;
		background-color: #fff;
		font-size: 24rpx;
	}
	.but_one{
		width: 131rpx;
		height: 62rpx;
		background-color: #ff6100;
		border-radius: 30px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 28rpx;
		color: #fff;
		position: absolute;
		left: 444rpx;
	}
	.but_two{
		width: 131rpx;
		height: 62rpx;
		background-color: #ff6100;
		border-radius: 30px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 28rpx;
		color: #fff;
	}
	.nav{
		width: 750rpx;
		height: 98rpx;
		background-color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		border-bottom: 1px solid #f5f5f5;
	}
	.nav_bar{
		width: 690rpx;
		height: 60rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-size: 24rpx;
	}
	.bar{
		width: 180rpx;
		height: 60rpx;
		border-radius: 30rpx;
		background-color: #ff6100;
		color: #fff;
		font-size: 24rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.index{
		width: 180rpx;
		height: 60rpx;
		border-radius: 30rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	
	
	
	
	.computer_list{
		width: 690rpx;
		margin: 0 auto;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
	}
	.computer{
		width: 335rpx;
		height: 443rpx;
		border: 1px solid #f5f5f5;
		border-radius: 10px;
		margin-top: 22rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.computer image{
		width: 335rpx;
		height: 242rpx;
	}
	.computer p{
		font-size: 28rpx;
		font-weight: 900;
	}
	.computer text{
		font-size: 20rpx;
		margin-top: 10rpx;
	}
	.computer span{
		font-size: 28rpx;
		color: #e81717;
		font-weight: 900;
		margin-top: 40rpx;
	}
</style>
