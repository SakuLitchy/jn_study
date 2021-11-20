<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<navigator url="/pages/exam/exam"><button type="default" class="title">开始考试</button></navigator>
		</view>
	</view>
</template>

<script>
	
	 export default {
	        methods: {
	            goto(url) {
	                uni.navigateTo({
	                    url:url
	                })
	            }
	        }
	    }
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
	.confirm{
		width:325rpx;
		height:80rpx;
		background:#07c160;
		border-radius:6rpx;
		font-size: 30rpx;
		color:#FFFFFF;
		line-height:80rpx;
		text-align:center;
	}
	.bubble{
		position: relative;
		overflow:hidden;
	}
	.bubble:after{
		content: "44444";
		background: #5c9899;
		position: absolute;
		width: 750rpx;
		height: 750rpx;
		left:calc(50% - 375rpx);
		top: calc(50% - 375rpx);
		opacity: 0;
		margin: auto;
		border-radius: 50%;
		transform: scale(1);
		transition: all 0.5s ease-in-out;
	}
	.bubble:active::after

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 100rpx;
		color: #ffffff;
	}
	
</style>
