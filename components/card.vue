<template>
	<view class="bg-white">
		<view class="padding-sm">
			<text class="text-primary text-md text-bold">{{ title }}</text>
		</view>
		<slot></slot>
	</view>
</template>

<script>
export default {
	props: {
		title: String
	},
	data() {
		return {}
	}
}
</script>

<style lang="scss" scoped>

</style>
