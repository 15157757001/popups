<template>
	<view class="content">
		<view class="light">
			<text @tap="taptext($event,1)">动态获取</text>
			<text @tap="value1=!value1">白色纵向</text>
		</view>
		<text>黑色横向</text>
		<view class="dark">
			<view>
				<text @tap="value2=!value2">top-start</text>
				
				<text @tap="value3=!value3">top-end</text>
			</view>
			<view>
				<text @tap="value4=!value4">bottom-start</text>
				<text @tap="value5=!value5">bottom-end</text>
			</view>
		</view>
		<chunLei-popups v-model="value0" :x="x" :y="y" dynamic>
			<view>插槽</view>
		</chunLei-popups>
		<chunLei-popups v-model="value1" :popData="data1" @tapPopup="tapPopup" :x="344" :y="20" placement="top-end">
			
		</chunLei-popups>
		<chunLei-popups v-model="value2" :popData="data2" @tapPopup="tapPopup" :x="66" :y="170" direction="row" theme="dark" >
			
		</chunLei-popups>
		<chunLei-popups v-model="value3" :popData="data2" @tapPopup="tapPopup" :x="303" :y="170" direction="row" theme="dark" placement="top-end">
			
		</chunLei-popups>
		<chunLei-popups v-model="value4" :popData="data2" @tapPopup="tapPopup" :x="84" :y="430" direction="row" theme="dark" placement="bottom-start">
			
		</chunLei-popups>
		<chunLei-popups v-model="value5" :popData="data2" @tapPopup="tapPopup" :x="302" :y="430" direction="row" theme="dark" placement="bottom-end">
			
		</chunLei-popups>
		<view class="light">
			<text @tap="taptext($event,1)">动态获取</text>
			<text @tap="taptext($event,1)">动态获取</text>
		</view>
	</view>
</template>

<script>
	import chunLeiPopups from "@/components/chunLei-popups/chunLei-popups.vue";
	export default {
		components:{
			chunLeiPopups
		},
		data() {
			return {
				value0:false,
				value1:false,
				value2:false,
				value3:false,
				value4:false,
				value5:false,
				x:0,
				y:0,
				data1:[
					{
						title:'创建群聊',
						icon:'../../static/chuangjianqunliao-lan.png'
					},
					{
						title:'加好友/群',
						icon:'../../static/tianjiahaoyou.png'
					},
					{
						title:'扫一扫',
						icon:'../../static/scan_icon.png'
					},
					{
						title:'面对面快传',
						icon:'../../static/zhifeiji.png'
					},
					{
						title:'收付款',
						icon:'../../static/shoufukuan.png'
					}
				],
				data2:[{title:'复制'},{title:'转发'},{title:'回复'},{title:'删除'}]
			}
		},
		onLoad() {

		},
		mounted() {
		
		},
		methods: {
			tapPopup(e){
				uni.showToast({
					title:e.title,
					icon:'none'
				})
			},
			taptext(e,index){
				console.log(e,index)
				this.x = e.touches[0].clientX
				this.y = e.touches[0].clientY
				this.value0 = !this.value0
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		font-size:16px;
		.light{
			display: flex;
			width: 100%;
			justify-content: space-between;
			margin-bottom:150rpx;
		}
		.dark{
			margin-bottom:150rpx;
			padding: 50rpx;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			height: 600rpx;
			width: 80%;
			view{
				display: flex;
				justify-content: space-between;
			}
		}
	}

</style>
