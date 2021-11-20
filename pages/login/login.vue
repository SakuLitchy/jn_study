<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>

		
		<view>
			<view class="input-fa">
				<input class="log-input" placeholder="用户名/邮箱/手机号" v-model="form.phone"/>
			</view>
			<view class="input-fa">
				<input class="log-input" placeholder="请输入密码" v-model="form.password":password="true"/>
			</view>
		</view>
		<view style="margin-top: 40upx;" class="flex justify-center">
			<button @tap="login" class="uni-bg-red round" style="width:650upx">
				登录
			</button>
		</view>
		<view class="flex justify-between input-fa" style="margin-top: 30upx;">
			<text>新用户注册</text>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				form:{
					phone:"",
					password:""
				}
			}
		},
		methods:{
			login(){
				uni.request({ /* 网络接口 */
					url:"",
					data:{
						phone:this.form.phone,
						password:this.form.password
					},
					method:"POST",
					success: (res) => {
						uni.showToast({
							icon:"none",
							title:res.data.desc
						})
						console.log(res.data)
						if(res.data.status==0){
							uni.setStorageSync("uid",res.data.uid);
							uni.navigateTo({
								url:"../index/index"
							})
						}
					}
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
		margin-top: 130rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
	.log-input{
		height: 100upx;
		border-bottom: 1upx solid #DDDDDD;
	}
	.input-fa{
		padding:40upx 40upx 40upx 40upx
	}
</style>