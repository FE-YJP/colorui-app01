<template>
<view>
	<cu-custom bgColor="bg-gradual-blue" :isBack="true">
		<block slot="backText"></block>
		<block slot="content">签到</block>
		<block slot="right">
			<!-- <text class="cuIcon-more"></text> -->
		</block>
	</cu-custom>
	

  <view class="calendar flex justify-center">
    <button class="cu-btn round margin bg-gradual-blue" @click="signIn">
		<text class="text-white">{{signText}}</text>
	</button>
    
  </view>
  <ss-calendar :checks="checks" />
</view>
</template>

<script>
  import ssCalendar from '@/components/ss-calendar/ss-calendar.vue'
  export default {
    data() {
      return {
        checks: [1,3],
		signText:"点击签到"
      };
    },
    components: {
      ssCalendar
    },
    methods: {
      signIn() {
		  
        const day = new Date().getDate()
        this.checks.push(day)
		uni.showToast({
			title: '签到成功!',
			duration: 1000,
			icon:"none",
		});
		this.signText="已签到";
		console.log(day)
		console.log(this.checks);
      }
    }
  }
</script>

<style lang="scss" scoped>
  .calendar {
    background-color: #fff;
    .btn-sign-in {
      width: 240upx;
      height: 70upx;
      line-height: 70upx;
      text-align: center;
      border: 2upx solid #ddd;
      border-radius: 43upx;
      margin: 0 auto;
      font-size: 32upx;
    }
  }
</style>
