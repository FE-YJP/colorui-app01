<template>
<view>
<!-- 自定义头部 -->
<!-- 
<cu-custom bgColor="bg-gradual-blue" :isBack="true" bgImage="">
	<block slot="backText">返回</block>
	<block slot="content">导航栏</block>
	<block slot="right">右侧区域</block>
</cu-custom>
-->
<view class="cu-bar bg-gradual-blue search">
	<view class="cu-avatar round" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big11010.jpg">
	</view>
	<view class="search-form radius">
		<text class="cuIcon-search"></text>
		<input @focus="InputFocus" @blur="InputBlur" :adjust-position="false" type="text" placeholder="搜索图片、文章、视频" confirm-type="search"></input>
	</view>
	<view class="action">
		<text class="cuIcon-edit"></text>
		<text>签到</text>
	</view>
</view>
<!-- 普通轮播 -->
<view class="margin radius" style="overflow: hidden;">

<swiper class="screen-swiper" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true" :autoplay="true" interval="5000" duration="500">
	<swiper-item v-for="(item,index) in swiperList" :key="index">
	<image :src="item.url"  mode="aspectFill" v-if="item.type=='image'"></image>		
	</swiper-item>
</swiper>

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
				}]
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
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			},
			InputBlur(){
				
			}
			
			
		}
	}
</script>

<style>

</style>
