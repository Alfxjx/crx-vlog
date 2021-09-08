<template>
	<div class="wrapper">
		<div class="tab">
			<el-card class="tab-card">
				<div class="logo">
					<img src="../../static/icons/128.png" width="50%" alt="" srcset="" />
				</div>
				<div class="hint">
					<el-alert
						type="info"
						center
						title="input the name of the video"
						:closable="false"
					></el-alert>
				</div>	
				<el-input v-model="name"></el-input>
				<el-button class="btns" type="primary" @click="startRecorder()"
					>Start</el-button
				>
				<el-button class="btns" type="danger" plain @click="stopRecorder()"
					>Stop</el-button
				>
			</el-card>
			<el-card class="tab-desc">
				<div class="img">
					<img src="../../static/example.gif" width="600px" alt="" />
				</div>
				<el-alert
					type="success"
					effect="dark"
					show-icon
					center
					title="click Stop or browser stop to stop and download the video"
					:closable="false"
				></el-alert>
			</el-card>
		</div>
		<div class="bot">
			<div class="source">
				<a
					href="https://github.com/Alfxjx/crx-vlog"
					target="_blank"
					rel="noopener noreferrer"
					>GitHub: crx-vlog</a
				>
				<a href="mailto:xjxtju@163.com">Email: xjxtju@163.com</a>
			</div>
		</div>
	</div>
</template>

<script>
import { Vlog } from "console-vlog/dist/bundle.esm";

export default {
	data() {
		return {
			name: "video",
			recorder: null,
		};
	},
	mounted() {
		document.title = "EasyRecorder";
	},
	methods: {
		startRecorder() {
			this.recorder = new Vlog({ name: this.name });
			this.recorder.start();
		},
		stopRecorder() {
			this.recorder.stop();
		},
	},
};
</script>
<style lang="scss">
body {
	margin: 0;
}
.wrapper {
	width: 100%;
	height: 100vh;
	display: flex;
	flex-direction: column;
	.tab {
		flex: 1;
		display: flex;
		justify-content: space-evenly;
		align-items: center;
		&-card {
			width: 18rem;
			height: 27rem;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			.logo {
				margin-bottom: 1.5rem;
				display: flex;
				justify-content: center;
			}
			.hint {
				margin: 0.5rem 0;
			}
			.btns {
				width: 100%;
				margin: 1rem 0 0 0;
			}
		}
		&-desc {
			display: flex;
			flex-direction: column;
			align-items: center;
		}
	}
	.bot {
		flex: 0;
		width: 100%;
		background: #678;
		color: #e2e4e6;
		display: flex;
		justify-content: center;
		.source {
			height: 3rem;
			display: flex;
			justify-content: space-around;
			align-items: center;
			a {
				color: #e2e4e6;
				text-decoration: none;
				margin: 0 1rem 0 0;
				&:hover {
					text-decoration: underline;
				}
			}
		}
	}
}
</style>
