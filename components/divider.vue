<template>
	<view :style="{ backgroundColor: color, height: height + 'rpx' }"/>
</template>

<script>
export default {
	props: {
		color: {
			type: String,
			default: '#f3f6fc'
		},
		height: {
			type: Number,
			default: 10
		}
	}
}
</script>

<style></style>
