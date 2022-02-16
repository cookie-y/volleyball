<template>
	<view class="transition">
		<u-image src="/static/transition.png" :fade="true" duration="450" height="300" width="100"
			@load="toLogin"/>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				timer: null
			}
		},
		methods: {
			toLogin() {
				this.timer = setTimeout(() => {
					uni.redirectTo({
						url: "./login"
					})
				}, 3000)
			}
		},
		unmounted() {
			clearTimeout(this.timer)
		}
	}
</script>

<style>
.transition /deep/ .u-image {
	margin: 0 auto;
}
</style>
