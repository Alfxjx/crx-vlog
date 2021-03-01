<template>
	<div>
		<el-button type="primary" @click="tab()">ACTION</el-button>
	</div>
</template>
<script>
import { Vlog } from "console-vlog/dist/bundle.esm";
export default {
	data() {
		return {
			recorder: null,
		};
	},
	computed: {},
	created() {},
	mounted() {
		this.recorder = new Vlog({ name: "download" });
	},
	methods: {
		tab() {
			// chrome.tabs.create({ url: "pages/app.html" });
      this.recorder.start();
		},
	},
};
</script>
<style lang="scss">
div {
	color: blue;
  width: 80rem;
  height: 40rem;
}
</style>
