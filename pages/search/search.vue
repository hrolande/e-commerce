<template>
	<view>
		<card :title="'热门搜索'">
			<view style="height: 300rpx;"><image style="height: 300rpx;" src="../../static/images/demo/demo4.jpg"></image></view>
		</card>
		<view class="bg-white padding">
			<block v-for="(item, index) in hot" :key="index">
				<view class="inline-block padding-xs margin-xs bg-white text-sm boder">{{ item.name }}</view>
			</block>
		</view>
		<card :title="'常用分类'">
			<view class="padding-horizontal padding-bottom">
				<block v-for="(item, index) in hot" :key="index">
					<view class="inline-block padding-xs margin-xs bg-gray text-sm text-regular">{{ item.name }}</view>
				</block>
			</view>
		</card>
		<divider />
		<card :title="'搜索记录'">
			<view class="border-top padding" v-for="(item, index) in history" :key="index">{{ item.name }}</view>
		</card>
	</view>
</template>

<script>
import divider from '@/components/divider'
import card from '@/components/card'
export default {
	components: {
		divider,
		card
	},
	data() {
		return {
			hot: [
				{
					name: 'Iphone'
				},
				{
					name: 'MacBook'
				},
				{
					name: 'Apple Watch '
				},
				{
					name: 'AirPods2'
				}
			],
			history: [{ name: 'Iphone 11 Max Pro' }, { name: 'Apple Watch Series5' }]
		}
	},
	methods: {}
}
</script>

<style></style>
