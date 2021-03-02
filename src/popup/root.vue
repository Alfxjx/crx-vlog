<template>
	<div class="pop">
		<span class="hint">
			<img src="../../static/icons/16.png" alt="" srcset="" />
			Click to Start</span
		>
		<el-button style="width:100%" type="primary" round @click="tab()"
			>Start</el-button
		>
	</div>
</template>

<script>
export default {
	mounted() {},
	methods: {
		tab() {
			chrome.tabs.create({ url: "pages/app.html" });
		},
	},
};
</script>
<style lang="scss">
.pop {
	width: 10rem;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	.hint {
		margin: 1rem 0;
		display: flex;
		align-items: center;
		img {
			margin: 0 0.5rem 0 0;
		}
	}
}
</style>
