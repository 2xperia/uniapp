<template>
	<view>
		<view class="header">
			<view class="box">
				<image class="image" src="../../static/查找.png" mode=""></image>
				<input v-model="value" :type="type" :border="border" placeholder="12344"/>
			</view>
			<view class="locate" @click="findLocation">
				<image class="images" src="../../static/定位.png" mode=""></image>
				<text class="text">{{location}}</text>
				<text class="text">{{delta.city_name}}</text>
			</view>
			<view class="map" @click="findMap">
				<image class="images" src="../../static/地图.png" mode=""></image>
				<text class="text">{{map}}</text>
			</view>
		</view>
		<view class="middle">
			
		</view>
		<view class="empty" v-if="location == '某城市'">
			<image class="search" src="../../static/查找文件.png" mode=""></image>
			<view class="button">
				<button class="lcick" type="default"@click="findLocation">手动按区域搜索</button>
			</view>
		</view>
		<view  v-if="location != '某城市'">
			<view class="element">
				<text>安定门支行</text>
				<view class="">
					<image class="images" src="../../static/定位.png" mode=""></image>
					<text>北京市东城区交通口南大街18号</text>
					<image src="../../static/向右1.png" mode=""></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			delta:{
				type:Object
			}
		},
		data() {
			return {
				value: '',
				type: 'text',
				border: true,
				location:"某城市",
				map:'地图',
				list:[]
			}
		},
		methods: {
			findLocation(){
				uni.navigateTo({
					url:"../location/location"
				})
			},
			findMap(){
				console.log('asd',this.delta)
				uni.navigateTo({
					url:"../map/map"
				})
			},
			otherFun(object){
			
			this.location = object.city_name
			
			}
		},
		mounted() {
			
		}
	}
</script>

<style>
	.box{
		margin: 20rpx;
		padding: 10rpx;
		display: flex;
		background-color: #e3e8f1;
		border-radius: 8rpx;
		width: 75%;
		height:50rpx
	}
	.header{
		display: flex;
	}
	.image{
		height: 35rpx;
		width: 35rpx;
		margin: 5rpx;
	}
	.images{
		height: 40rpx;
		width: 42rpx;
		margin: 0px;
		padding-top: 10px;
	}
	.locate{
		margin: 0 auto;
		text-align: center;
		width: 70rpx;
		height:60rpx
	}
	.map{
		margin: 0 auto;
		width: 50rpx;
		margin-left: 20px;
		margin-right: 30px;
	}
	.text{
		font-size: 20rpx;
		margin-top: -20rpx;
	}
	.middle{
		width: 100%;
		height: 20rpx;
		background-color: #e3e3e3;
	}
	.empty{
		margin: 0 auto;
		text-align: center;
	}
	.search{
		width: 300rpx;
		height: 300rpx;
		margin-top: 50rpx;
		margin-bottom: 50rpx;
	}
	.lcick{
		width: 400rpx;
		height: 100rpx;
		border-radius: 20rpx;
		color: #19BE6B;
		;
	}
</style>
