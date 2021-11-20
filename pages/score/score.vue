<template>
	<view class="content">
        <text class="score">分数：</text>
		<view class="errorSubject">
			<navigator url="/pages/setting/errorSubject"><button type="default" class="title">查看错题记录表</button></navigator>
		</view>
	</view>
</template>

<script>
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
    .text-area {
		display: flex;
		justify-content: center;
	}
    .score{
		font-size: 50rpx;
	}
	.title {
		font-size: 50rpx;
		color: #ffffff;
	}
</style>
