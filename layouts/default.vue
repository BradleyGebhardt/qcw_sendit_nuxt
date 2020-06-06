<template>
	<div class="app-content">
		<s-nav-drawer :expanded="nav" />
		<s-app-bar>
			<button
				:class="{ ni: true, ni__expanded: nav }"
				@click="nav = !nav"
			>
				<s-nav-icon />
			</button>
		</s-app-bar>
		<nuxt />
	</div>
</template>

<script>
export default {
	name: 'DefaultLayout',

	data() {
		return {
			nav: false,
		}
	},

	methods: {},
}
</script>

<style lang="scss" scoped>
.app-content {
	height: 100vh;
}

.ni {
	margin-left: auto;
	margin-right: 10px;
	background-color: #ffffff00;
	border: none;
	transition: all 0.3s ease;

	&__expanded {
		margin-right: 210px;
	}
}

.ni:focus {
	outline: none;
}
</style>
