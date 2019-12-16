<template>
	<view>
		<!--顶部选项卡-->
		<scroll-view scroll-x class="border-bottom scroll-row bg-white" :scroll-into-view="scrollinto" scroll-with-animation>
			<view
				v-for="(item, index) in tabbars"
				:key="index"
				:id="'tab_' + index"
				@tap="onTabTap(index)"
				class="scroll-row-item padding-horizontal"
				style="height: 80rpx;line-height: 80rpx;"
			>
				<text class="text-md" :class="activeTab === index ? 'text-orange' : 'text-primary'">{{ item.name }}</text>
			</view>
		</scroll-view>
		<swiper duration="300" :current="activeTab" :style="{ height: scrollHeight + 'px' }" @change="onTabChange">
			<swiper-item v-for="(item, index) in tabbars" :key="index">
				<scroll-view scroll-y :style="{ height: scrollHeight + 'px' }">
					<swiper-image :images="bannerImgs"></swiper-image>
					<view class="flex flex-wrap padding bg-white">
						<view class="flex flex-direction justify-center align-center basis-xs nav-item" v-for="(item, index) in navItems" :key="index">
							<image class="nav-item-image" :src="item.imgUrl" />
							<text class="text-black text-sm">{{ item.title }}</text>
						</view>
					</view>
					<divider/>
					<view class="flex bg-white">
						<image class="border-extral-light margin-right-xs" style="height: 370rpx;width: 370rpx;" src="../../static/images/demo/demo1.jpg" lazy-load></image>
						<view class="flex flex-direction bg-white">
							<image class="border-extral-light margin-bottom-xs" style="height: 180rpx;width: 370rpx;" src="../../static/images/demo/demo2.jpg" lazy-load />
							<image style="height: 180rpx;width: 370rpx;" src="../../static/images/demo/demo2.jpg" lazy-load />
						</view>
					</view>
					<divider />
					<view class="card bg-white">
						<view class="padding-sm"><text class="text-primary text-md text-bold">每日精选</text></view>
						<view><image style="height: 300rpx;" src="../../static/images/demo/demo4.jpg"></image></view>
					</view>
					<divider />
					<view>
						<view class="bg-white" style="width: 372.5rpx;">
							<image src="../../static/images/demo/list/1.jpg" />
							<view class="padding-horizontal-sm padding-bottom-sm">
								<view class="text-lg">米家空调</view>
								<text class="text-secondary text-md text-cut">1.5匹变频空调</text>
								<view>
									<text class="text-price text-orange margin-right-xs text-md">1366</text>
									<text class="text-price text-grey text-sm text-through">2699</text>
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</swiper-item>
		</swiper>

	</view>
</template>

<script>
import swiperImage from '@/components/index/swiper-image'
import divider from '@/components/divider'
export default {
	components: {
		swiperImage,
		divider
	},
	data() {
		return {
			scrollHeight: 0,
			activeTab: 0,
			scrollinto: '',
			tabbars: [
				{
					name: '关注'
				},
				{
					name: '推荐'
				},
				{
					name: '体育'
				},
				{
					name: '热点'
				},
				{
					name: '财经'
				},
				{
					name: '娱乐'
				},
				{
					name: '军事'
				},
				{
					name: '科技'
				},
				{
					name: '广州'
				}
			],
			bannerImgs: [
				{
					src: '/static/images/demo/demo4.jpg'
				},
				{
					src: '/static/images/demo/demo4.jpg'
				},
				{
					src: '/static/images/demo/demo4.jpg'
				}
			],
			navItems: [
				{
					imgUrl: '/static/images/indexnav/1.png',
					title: '新品分类'
				},
				{
					imgUrl: '/static/images/indexnav/2.gif',
					title: '小米众筹'
				},
				{
					imgUrl: '/static/images/indexnav/3.gif',
					title: '以旧换新'
				},
				{
					imgUrl: '/static/images/indexnav/4.gif',
					title: '1分拼团'
				},
				{
					imgUrl: '/static/images/indexnav/5.gif',
					title: '超值特卖'
				},
				{
					imgUrl: '/static/images/indexnav/6.gif',
					title: '小米秒杀'
				},
				{
					imgUrl: '/static/images/indexnav/7.gif',
					title: '真心想要'
				},
				{
					imgUrl: '/static/images/indexnav/8.gif',
					title: '电视热卖'
				},
				{
					imgUrl: '/static/images/indexnav/9.gif',
					title: '家电热卖'
				},
				{
					imgUrl: '/static/images/indexnav/10.gif',
					title: '米粉卡'
				}
			]
		}
	},
	methods: {
		//选项卡tap
		onTabTap(index) {
			if (this.activeTab === index) {
				return
			}
			this.activeTab = index
			this.scrollinto = 'tab_' + index
		},
		//swiper滑动
		onTabChange(e) {
			this.activeTab = e.detail.current
			this.scrollinto = 'tab_' +  e.detail.current
		}
	},
	onLoad() {
		uni.getSystemInfo({
			success: res => {
				this.scrollHeight = res.windowHeight - uni.upx2px(80)
			}
		})
	}
}
</script>

<style scoped lang="scss">
.nav-item {
	height: 120rpx;
	.nav-item-image {
		width: 58rpx;
		height: 58rpx;
	}
}
</style>
