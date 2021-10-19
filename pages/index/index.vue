<template>
	<view class="content">
		<view class="imagebox">
			<image class="logo" src="/static/beijing.png"></image>
		</view>
		<view class="text-area">
			<view class="title">
				<text>预约开户申请</text>
			</view>
		</view>
		<view class="form">
			<view class="cell">
				<text class="titleText">统一社会信用代码</text>
				<input type="text" value="" placeholder="请手动输入" class="input" placeholder-class="placeholder" />
				<image src="../../static/扫一扫.png" mode="" class="scan" @click="scan"></image>
			</view>
			<view class="cell">
				<text class="titleText">企业名称</text>
				<input type="text" value="" class="input" />
			</view>
			<view class="cell">
				<text class="titleText">币种</text>
				<input type="text" value="" disabled placeholder="人民币" class="input" placeholder-class="placeholder" />
			</view>
			<view class="cell">
				<text class="titleText">开户网点选择</text>
				<image src="../../static/下拉.png" mode="" class="down" @click="point"></image>
			</view>
			<view class="cell">
				<text class="titleText">联系人姓名</text>
				<input type="text" value="" placeholder="请输入联系人姓名" class="input" placeholder-class="placeholder" />
			</view>
			<view class="cell">
				<text class="titleText">联系人手机号码</text>
				<input type="text" value="" placeholder="请输入联系人手机号码" class="input" placeholder-class="placeholder" />
			</view>
			<view class="cell">
				<text class="titleText">验证码</text>
				<button size="mini" type="primary" class="button">获取验证码</button>
			</view>
		</view>
		<view class="choose">
			<button  class="submit1">重置</button>
			<button  class="submit2">提交</button>	
		</view>
		<view class="box">
			<view class="boxs">
				<view class="back">
					<image src="../../static/查找.png" mode="" class="downimage"></image>
				</view>
				<view class="text">
					<text>进度查询</text>
				</view>
			</view>
			<view class="boxs" @click="list">
				<view class="back">
					<image src="../../static/清单.png" mode="" class="downimage"></image>
				</view>
				<view class="text">
					<text>资料清单</text>
				</view>
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hellos'
			}
		},
		onLoad() {

		},
		methods: {
			scan(){
				var _this = this;
				    uni.scanCode({
				　　　　　onlyFromCamera: true, //为true只允许相机扫码，不加允许相册扫码
				        success: function(res) {
				            uni.showToast({
				                title: '扫码成功'
				            })
				        },
				        fail: function(err) {
				            console.log('扫码失败', err)
				        }
				    })
			},
			list(){
				uni.navigateTo({
					url:"../list/list"
				})
			},
			point(){
				uni.navigateTo({
					url:"../point/point"
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
	}

	.logo {
		height: 150rpx;
		width: 300rpx;
	}
	.scan{
		height: 45rpx;
		width: 45rpx;
	}
	.down{
		height: 45rpx;
		width: 45rpx;
		margin-left: auto;
	}
	.text-area {
		border-left-style:solid;
		border-left-width: 12rpx;
		border-left-color: red;
		margin-left: 10rpx;
	}

	.title {
		font-size: 36rpx;
		margin-left: 6rpx;
		color: black;
		font-weight: 700;
	}
	.imagebox{
		height: 150rpx;
		width: 100%;
		margin-right: auto;
		margin-bottom: 40rpx;
		background-color: rgba(243,243,243);
	}
	.form{
		width: 93%;
	}
	.input{
		margin-left: auto;
		text-align:right;
		padding-right: 10rpx;
	}
	.cell{
		display: flex;
		margin: 10px;
		margin-top: 30rpx;
		width: 100%;
		height:70rpx;
		border-bottom-style:solid;
		border-bottom-width: 4rpx;
		border-bottom-color: #d7d7d7;
	}
	.titleText{
		font-weight: 600;
	}
	.button{
		margin-right: 0px;
		margin-top:-3px;	
		width: 100px;
		height:30px;	
		/* margin-bottom: 12px;
		padding-top: 6px; */
		font-size: 15px;
		background-color: #2C405A;
		color: #4CD964;
		text-align: center;	
	}
	.choose{
		display: flex;
		margin-top: 50rpx;
	}
	.submit1{
		width: 150px;
		height:50px;
		background-color: #ffd8c1;
		font-weight: 500;
		color: #aa5500;
		
	}
	.submit2{
		width: 150px;
		height:50px;
		background-color: #d90000;
		font-weight: 500;
		color: white;
	}
	.box{
		display: flex;
		margin-top: 50rpx;
		/* text-align: center; */
	}
	.back{
		height: 90rpx;
		width: 90rpx;
		background-color: #e9e9e9;
		border-radius: 30px;
		margin: 0 auto;
		padding: 5rpx;
	}
	.downimage{
		height: 70rpx;	
		width: 70rpx;
		margin: 5px;
	}
	.boxs{
		width: 50%;
		display: block;
		text-align: center;
		justify-content: center;
		align-items: center;
	}
	.text{
		margin-top: 10px;
		font-weight: 600;
	}
</style>
