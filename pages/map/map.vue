<template>
	<view>
		<map id="Id" style="width:100%;height:85vh;" :latitude="latitude" :longitude="longitude" :markers="markers" @markertap="showMarker"></map>
		<view class="" v-show="message">
			<text>{{detailtitle}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				message:true,
			    Id:0,
		   　　 title: 'map', //地图标题
		   　　 latitude: 40.013305,  //纬度
		  　　  longitude: 118.685713, //经度
			    markers:[{
					id:1,	
					latitude:40.013305,
					longitude:118.685713,
					title:'某地点',	
					width:30,
					height:50,
					zIndex:999,
					// callout:{
					// 	content:'aili',
					// 	color:'red',
					// 	fontSize:30
					// }
					
				}],
				detailtitle:''
	　　　　　　//scale：5，//最小数，缩放范围最大，可见程度最大
	　　　　　　//scale：18，//最大数，缩放范围最小，可见程度最小
			}
		},
		methods: {
			showMarker(e){
				this.message = true
				for (let i in this.markers) {
					if(this.markers[i].id == e.markerId){
						this.detailtitle = this.markers[i].title
						console.log('sdf',this.detailtitle)
					}
				}
				
			},
			showMarkers(e){
				this.message = true
				console.log('qwerty',e)
				
			}
		}
	}
</script>

<style>

</style>
