<template>
<view class="content_box">
	<view class="cu-bar bg-gradual-blue search fixed">
		<!-- <view class="action">
			<text class="cuIcon-back"></text>
		</view> -->
		<view class="search-form radius">
			<text class="cuIcon-search"></text>
			<input @focus="InputFocus" @blur="InputBlur" :adjust-position="false" type="text" placeholder="搜索图片、文章、视频" confirm-type="search"></input>
		</view>
		<view class="action" @tap="Back">
			<text>取消</text>
		</view>
	</view>
	<!-- 大家都在搜 -->
	<view class="cu-bar bg-white solid-bottom">
		<view class='action'>
			<text class='cuIcon-emoji text-red'></text>
			<text>大家都在搜</text>
		</view>
	</view>
	<view class="padding-xs bg-white solid-bottom margin-bottom">
		<!-- <view class='cu-tag'>默认</view>
		<view class='cu-tag round'>椭圆</view> -->
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>张大仙</view>
		<view class='cu-tag radius margin-xs'>PDD</view>
		<view class='cu-tag radius margin-xs'>小说</view>
		<view class='cu-tag radius margin-xs'>王者荣耀</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>文章</view>
		<view class='cu-tag radius margin-xs'>水一大魔王</view>
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>千里迢迢</view>
		<view class='cu-tag radius margin-xs'>我家大师兄脑子有坑</view>
	</view>
	<!-- <view class="cu-card case">
		<view class="cu-item shadow">
			<view class="image">
				<image src="https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg" mode="widthFix"></image>
			</view>
		</view>
	</view> -->
	<!-- 卡片 -->
	<view class="cu-card dynamic">
		<view class="cu-item shadow">
			<view class="grid flex-sub  col-1" >
				<view class="bg-img only-img" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big10006.jpg);"></view>
			</view>
		</view>
	</view>
	
	
	
	
	<!-- 搜索历史 -->
	<view class="cu-bar bg-white solid-bottom">
		<view class='action'>
			<text class='cuIcon-time text-red'></text>
			<text>搜索历史</text>
		</view>
	</view>
	<view class="padding-xs bg-white solid-bottom  margin-bottom">
		<!-- <view class='cu-tag'>默认</view>
		<view class='cu-tag round'>椭圆</view> -->
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>张大仙</view>
		<view class='cu-tag radius margin-xs'>PDD</view>
		<view class='cu-tag radius margin-xs'>小说</view>
		<view class='cu-tag radius margin-xs'>王者荣耀</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>文章</view>
		<view class='cu-tag radius margin-xs'>水一大魔王</view>
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>千里迢迢</view>
		<view class='cu-tag radius margin-xs'>我家大师兄脑子有坑</view>
	</view>
	<!-- 探索发现-->
	<view class="cu-bar bg-white solid-bottom">
		<view class='action'>
			<text class='cuIcon-discover text-red'></text>
			<text>探索发现</text>
		</view>
	</view>
	<view class="padding-xs bg-white solid-bottom margin-bottom">
		<!-- <view class='cu-tag'>默认</view>
		<view class='cu-tag round'>椭圆</view> -->
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>张大仙</view>
		<view class='cu-tag radius margin-xs'>PDD</view>
		<view class='cu-tag radius margin-xs'>小说</view>
		<view class='cu-tag radius margin-xs'>王者荣耀</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>文章</view>
		<view class='cu-tag radius margin-xs'>水一大魔王</view>
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>千里迢迢</view>
		<view class='cu-tag radius margin-xs'>我家大师兄脑子有坑</view>
	</view>
	<!--推荐-->
	<view class="cu-bar bg-white solid-bottom">
		<view class='action'>
			<text class='cuIcon-activity text-red'></text>
			<text>推荐</text>
		</view>
	</view>
	<view class="padding-xs bg-white solid-bottom margin-bottom">
		<!-- <view class='cu-tag'>默认</view>
		<view class='cu-tag round'>椭圆</view> -->
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>张大仙</view>
		<view class='cu-tag radius margin-xs'>PDD</view>
		<view class='cu-tag radius margin-xs'>小说</view>
		<view class='cu-tag radius margin-xs'>王者荣耀</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>文章</view>
		<view class='cu-tag radius margin-xs'>水一大魔王</view>
		<view class='cu-tag radius margin-xs'>游戏</view>
		<view class='cu-tag radius margin-xs'>视频</view>
		<view class='cu-tag radius margin-xs'>千里迢迢</view>
		<view class='cu-tag radius margin-xs'>我家大师兄脑子有坑</view>
	</view>
	
</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		onLoad() {
		
		},
		methods: {
			InputFocus(e){
				
			},
			InputBlur(){
				
			},
			Back(){
				uni.navigateTo({
					url: '/pages/index/index',
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
			}
		}
	}

</script>

<style>
.content_box{
	box-sizing: border-box;
	padding-top: 100upx;
}
</style>
