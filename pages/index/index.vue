<template>
<view class="content_box fixed">
<!-- 自定义头部 -->

<!-- <cu-custom bgColor="bg-gradual-blue" :isBack="true">
	<block slot="backText">返回</block>
	<block slot="content">首页</block>
	<block slot="right">
		<text class="cuIcon-more"></text>
	</block>
</cu-custom> -->


<view class="cu-bar bg-gradual-blue search system-status-bar fixed">
	<view class="cu-avatar round " style="background-image:url('../../static/logo.png')">
	<!-- <view class="cu-avatar round " style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big11010.jpg"> -->
	</view>
	<view class="search-form radius">
		<text class="cuIcon-search"></text>
		<input @click="InputFocus" @blur="InputBlur" :adjust-position="false" type="text" placeholder="搜索图片、文章、视频" confirm-type="search"
		disabled="true"></input>
	</view>
	<view class="action" @click="Sign">
		<text class="cuIcon-edit"></text>
		<text>签到</text>
	</view>
</view>

<!-- 普通轮播 -->
<view class="system-margin">
<view class="margin radius " style="overflow: hidden;">

<swiper class="screen-swiper" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true" :autoplay="true" interval="5000" duration="500">
	<swiper-item v-for="(item,index) in swiperList" :key="index">
	<image :src="item.url"  mode="aspectFill" v-if="item.type=='image'"></image>		
	</swiper-item>
</swiper>

</view>
</view>

<!-- 卡片轮播 -->
<swiper class="card-swiper" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true" :autoplay="true" interval="5000" duration="500" @change="cardSwiper" indicator-color="#8799a3"
 indicator-active-color="#0081ff">
<swiper-item v-for="(item,index) in swiperList" :key="index" :class="cardCur==index?'cur':''">
	<view class="swiper-item">
		<image :src="item.url" mode="aspectFill" v-if="item.type=='image'"></image>
		<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video>
	</view>
</swiper-item>
</swiper>
<view class="cu-bar bg-white margin-top">
	<view class="action">
		<text class="cuIcon-title text-pink"></text> 卡片式轮播
	</view>
</view>
<view class="cu-bar bg-white">
	<view class="action">
		<text class="cuIcon-title text-pink"></text> 全屏限高轮播
	</view>
	<view class="action">
		<switch @change="DotStyle" :class="dotStyle?'checked':''" :checked="dotStyle?true:false"></switch>
	</view>
</view>

<view class="cu-form-group">
				<view class="title">时间选择</view>
				<picker mode="time" :value="time" start="09:01" end="21:01" @change="TimeChange">
					<view class="picker">
						{{time}}
					</view>
				</picker>
			</view>
			<view class="cu-form-group">
				<view class="title">日期选择</view>
				<picker mode="date" :value="date" start="2015-09-01" end="2020-09-01" @change="DateChange">
					<view class="picker">
						{{date}}
					</view>
				</picker>
			</view>



</view>
</template>

<script>
	export default {
		data() {
			return {
				cardCur: 0,
				towerStart: 0,
				direction: '',
				dotStyle: true,
				swiperList: [{
					id: 0,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
				}, {
					id: 1,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
				}, {
					id: 2,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
				}],
				time: '12:01',
				date: '2018-12-25',
			}
		},
		onLoad() {

		},
		methods: {
			DotStyle(e) {
				this.dotStyle = e.detail.value
			},
			// cardSwiper
			cardSwiper(e) {
				this.cardCur = e.detail.current
			},
			// search跳转搜索页
			InputFocus(e){
				console.log(e);
				uni.navigateTo({
					url: '/pages/index/search',
					animationType:"pop-in",
					animationDuration:300

				});
			},
			// 签到页面
			Sign(e){
				console.log(e);
				uni.navigateTo({
					url: '/pages/index/sign',
					animationType:"pop-in",
					animationDuration:300
				
				});
			},
			InputBlur(){
				
			},
			TimeChange(){
				
			},
			DateChange(){
				
			}
			
			
		}
	}
</script>

<style>

</style>
