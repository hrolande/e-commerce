<template>
	<view>
		<swiper class="swiper-image" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" circular>
			<swiper-item v-for="(img, index) in images" :key="index" @tap="onItemTap(item)">
				<view><image class="swiper-image-item" :src="img.src" mode="scaleToFill" lazy-load /></view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
export default {
	props: {
		images: Array
	},
	methods: {
		onItemTap(item) {
			console.log('点击了')
		}
	}
}
</script>

<style lang="scss" scoped>
.swiper-image {
	height: 300rpx;
	width: 750rpx;
	.swiper-image-item {
		width: 100%;
		width: 750rpx;
		height: 300rpx;
	}
}
</style>
