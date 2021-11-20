<template>
	<view class="page">
		<view class="header">
			<text class="leftTime">考试时长：60分钟</text>
			<text class="rightTime">00:10:10</text>
			<text class="rightTime">计时：</text>				
		</view>
		<view v-for="(item,index) in itemList" :key="item.id" class="subjectStyle">			
			<view>
				<text>{{index+1+'、'}}</text>
				<text>{{item.subjectContent}}</text>
			</view>
			<view class="uni-list">
			    <radio-group @change="radioChange">
			        <label class="uni-list-cell uni-list-cell-pd" v-for="(result, index) in item.answerList" :key="result.id">
						<view>
						<radio :value="result.id" :checked="index === current" />
						</view>
						<view class="answer">{{result.answerOption+'、'+result.answerContent}}</view>
					</label>
			    </radio-group>
			</view>
		</view>
		<view>
			 <button type="default" class="tijiao" @click="getList()">提交</button>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				itemList: []
			}
		},
		onLoad() {
			this.getList();
			
		},
		methods: {
			getList(){
				uni.request({
					url:"http://192.168.20.39:8081/subject",
					success:(res) => {
						
						this.itemList = res.data.data;
						console.log(JSON.stringify(res.data.data));
					}
				});
				uni.navigateTo({
					url: '../score/score',
				});
				
			}
		}
	}
</script>

<style>
	.header{
		height: 25px;
		width: 100%;
		background: #C0C0C0;
		
	}
	.leftTime{
		float: left;
		color: white;
		font-weight: 400;
		font-size: 13px;
	}
	.rightTime{
		float: right;
		color: white;
		font-weight: 400;
		font-size: 13px;
	}
	.subject{
		text-align: center;
		
	}
	.page{
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #ffffff;
		min-height: 100%;
		height: auto;
		font-size: 18px;
		font-weight: bold;
		margin-bottom: 30px;
		
	}
	.answer{
		margin-left: 0px;
		font-size: 15px;
		font-weight: 400;
	}
	.subjectStyle{
		margin: 15px 20px;
		border: 2px solid pink;
		border-radius: 10px;
		padding: 5px 5px;
	}
	.tijiao{
		margin: 15px 20px;
	}
</style>
