<template>
	<view class="page">
		<view class="yongHu uni-list-cell">
			<view>
				<image src="../../static/app_icon.png"></image>
					
			</view>
			<view>
				<text class="yongHuName">测试用户</text>
				
			</view>
			
		</view>
		<view class="list">			
			<uni-list>
				<uni-list-item title="错误记录" showArrow link="navigateTo" to="./errorSubject"/>
			</uni-list>
		</view>
		
	</view>
</template>

<script>
</script>

<style>
	image{
		height: 150rpx;
		width: 150rpx;
		margin: 15rpx 15rpx;
		border-radius: 50%;
	}
	.yongHu{
		width: 750rpx;
		height: 300rpx;
		background: white;
		
	}
	.yongHuName{
		text-align: center;
		font-size: 20px;
		font-weight: bold;
		margin-top: -80rpx;
		height: 100%;
		
	}
	.page{
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #efeff4;
		min-height: 100%;
		height: auto;
		
	}
	.list{
		margin-top: 30rpx;
	}
</style>
