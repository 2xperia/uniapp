<template>
	<view>
		<view class="topbar">
			<button  class="button" @click="submit(1)">基本账户</button>
			<button  class="button" @click="submit(2)">一般账户</button>
			<button  class="button" @click="submit(3)">专用账户</button>
			<button  class="button" @click="submit(4)">临时账户</button>
		</view>
		<view class="text-area">
			<view class="title">
				<text>必带资料</text>
			</view>
		</view>
		<view class="options" v-show="show == 1">
			<view class="text">
				<text>1、营业执照正、副本条件</text>
			</view>
			<view class="text">
				<text>2、法定代表人/负责人身份证原件</text>
			</view>
			<view class="text">
				<text>3、公章、财务章、法人名章</text>
			</view>
			<view class="text">
				<text>4、公司章程原件，最终受益人身份证原件</text>
			</view>
			<view class="text">
				<text>5、授权经办人身份证原件及单位授权书(如授权经办人办理)</text>
			</view>
		</view>
		<view class="options" v-show="show == 2">
			<view class="text">
				<text>1、营业执照正、副本条件</text>
			</view>
			<view class="text">
				<text>2、法定代表人/负责人身份证原件</text>
			</view>
			<view class="text">
				<text>3、公章、财务章、法人名章</text>
			</view>
			<view class="text">
				<text>4、公司章程原件，最终受益人身份证原件</text>
			</view>
			<view class="text">
				<text>5、基本户开户许可证正本</text>
			</view>
			<view class="text">
				<text>6、授权经办人身份证原件及单位授权书(如授权经办人办理)</text>
			</view>
		</view>
		<view class="text-area">
			<view class="title">
				<text>其他要求</text>
			</view>
		</view>
		<view class="options" v-if="show == 1">
			<view class="text">
				<text>1、如经营地与注册地不一致,还应提供经营地房产证或房屋租赁合同等能证明单位合法使用的文件</text>
			</view>
			<view class="text">
				<text>2、如为国家管控许可类企业,须提供相应许可证正本(如金融许可证、基金许可证等)</text>
			</view>
			<view class="text">
				<text>3、如有上级法人或主管单位,须提供证明文件:公章、营业执照、开户许可证、法人身份证</text>
			</view>
			<view class="text">
				<text>4、如为预算单位,还需提供同级财政主管部门批文</text>
			</view>
			<view class="text">
				<text>5、如有其他问题,请详询开户行</text>
			</view>
		</view>
		<view class="options" v-show="show == 2">
			<view class="text">
				<text>1、如经营地与注册地不一致,还应提供经营地房产证或房屋租赁合同等能证明单位合法使用的文件</text>
			</view>
			<view class="text">
				<text>2、如为国家管控许可类企业,须提供相应许可证正本(如金融许可证、基金许可证等)</text>
			</view>
			<view class="text">
				<text>3、如有上级法人或主管单位,须提供证明文件:公章、营业执照、开户许可证、法人身份证</text>
			</view>
			<view class="text">
				<text>4、如为预算单位,还需提供同级财政主管部门批文</text>
			</view>
			<view class="text">
				<text>5、如因借款原因开立的,需提供借款合同</text>
			</view>
			<view class="text">
				<text>6、如有其他问题,请详询开户行</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:true
			}
		},
		methods: {
			submit(num){
				this.show = num
			},
			
		}
	}
</script>

<style>
	.topbar{
		display: flex;
		margin-top: 25px;
		width: 95%;
		height: 40px;
		margin: 0 auto;
		border-bottom-style:solid;
		border-bottom-width: 4rpx;
		border-bottom-color: #d7d7d7;
	}
	.button{
		width: 70px;
		height:30px;
		background-color: #ffd8c1;
		font-size: 11px;
		padding: 5rpx;
		color: #aa5500;
	}
	.text-area {
		margin: 20px;
		border-left-style:solid;
		border-left-width: 12rpx;
		border-left-color: red;
		margin-left: 10rpx;
	}
	
	.title {
		font-size: 30rpx;	
		margin-left: 6rpx;
		color: black;
		font-weight: 700;
	}
	.options{
		margin-left: 30rpx;
		width: 90%;
	}
	.text{
		margin-top: 10rpx;
	}
</style>
